---
title: Přeformátování kódu ve službě starší verze jazyka | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- reformatting code, supporting in language services [managed package framework]
- language services [managed package framework], reformatting code
ms.assetid: 08bb3375-8fef-4f4e-9efa-0d7333bab0eb
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: ae48e1b97b5c9194cf3081687ab31ea9f857e6c9
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/22/2019
ms.locfileid: "72724761"
---
# <a name="reformatting-code-in-a-legacy-language-service"></a>Přeformátování kódu ve službě starší verze jazyka

Ve zdrojovém kódu [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] lze přeformátovat normalizací použití odrážek a prázdných znaků. To může zahrnovat vložení nebo odebrání mezer nebo karet na začátku každého řádku, přidání nových řádků mezi řádky nebo nahrazení mezer tabulátory nebo tabulátory mezerami.

> [!NOTE]
> Vložení nebo odstranění znaků nového řádku může ovlivnit značky, jako jsou zarážky a záložky, ale přidávání nebo odebírání mezer nebo karet nemá vliv na značky.

Uživatelé mohou operaci přeformátování spustit výběrem možnosti **Formátovat výběr** nebo **formátovat dokument** z nabídky **Upřesnit** v nabídce **Upravit** . Operaci přeformátování lze také aktivovat při vložení fragmentu kódu nebo konkrétního znaku. Když například zadáte pravou složenou závorku v C#, vše mezi odpovídající levou složenou závorkou a pravou složenou závorkou se automaticky odsadí na správnou úroveň.

Když [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] odešle do služby jazyka příkaz **Format Selection** nebo **Format Document** , třída <xref:Microsoft.VisualStudio.Package.ViewFilter> volá metodu <xref:Microsoft.VisualStudio.Package.Source.ReformatSpan%2A> ve třídě <xref:Microsoft.VisualStudio.Package.Source>. Pro podporu formátování musíte přepsat metodu <xref:Microsoft.VisualStudio.Package.Source.ReformatSpan%2A> a dodat vlastní kód formátování.

## <a name="enabling-support-for-reformatting"></a>Povolení podpory pro přeformátování

Aby bylo možné podporovat formátování, musí být parametr `EnableFormatSelection` <xref:Microsoft.VisualStudio.Shell.ProvideLanguageServiceAttribute> při registraci VSPackage nastaven na hodnotu `true`. Tím se vlastnost <xref:Microsoft.VisualStudio.Package.LanguagePreferences.EnableFormatSelection%2A> nastaví na hodnotu `true`. Metoda <xref:Microsoft.VisualStudio.Package.ViewFilter.CanReformat%2A> vrací hodnotu této vlastnosti. Pokud vrátí hodnotu true, třída <xref:Microsoft.VisualStudio.Package.ViewFilter> volá <xref:Microsoft.VisualStudio.Package.Source.ReformatSpan%2A>.

## <a name="implementing-reformatting"></a>Implementace přeformátování

Chcete-li implementovat přeformátování, je nutné odvodit třídu z třídy <xref:Microsoft.VisualStudio.Package.Source> a přepsat metodu <xref:Microsoft.VisualStudio.Package.Source.ReformatSpan%2A>. Objekt <xref:Microsoft.VisualStudio.TextManager.Interop.TextSpan> popisuje rozsah pro formátování a objekt <xref:Microsoft.VisualStudio.Package.EditArray> obsahuje úpravy provedené v rozpětí. Všimněte si, že tento rozsah může být celý dokument. Vzhledem k tomu, že v rozpětí jsou pravděpodobně provedeny různé změny, všechny změny by měly být v jedné akci vratné. To provedete tak, že zabalíte všechny změny v objektu <xref:Microsoft.VisualStudio.Package.CompoundAction> (viz část "použití třídy CompoundAction" v tomto tématu).

### <a name="example"></a>Příklad

Následující příklad zajišťuje jedno místo za každou čárkou ve výběru, pokud čárka není následována tabulátorem nebo na konci řádku. Koncové mezery za poslední čárkou na řádku se odstraní. Informace o tom, jak je tato metoda volána z metody <xref:Microsoft.VisualStudio.Package.Source.ReformatSpan%2A>, naleznete v části "použití třídy CompoundAction" v tomto tématu.

```csharp
using Microsoft.VisualStudio.Package;
using Microsoft VisualStudio.TextManager.Interop;

namespace MyLanguagePackage
{
    class MySource : Source
    {
        private void DoFormatting(EditArray mgr, TextSpan span)
        {
            // Make sure there is one space after every comma unless followed
            // by a tab or comma is at end of line.
            IVsTextLines pBuffer = GetTextLines();
            if (pBuffer != null)
            {
                int    startIndex = span.iStartIndex;
                int    endIndex   = 0;
                string line       = "";
                // Loop over all lines in span
                for (int i = span.iStartLine; i <= span.iEndLine; i++)
                {
                    if (i < span.iEndLine)
                    {
                        pBuffer.GetLengthOfLine(i, out endIndex);
                    }
                    else
                    {
                        endIndex = span.iEndIndex;
                    }
                    pBuffer.GetLineText(i, startIndex, i, endIndex, out line);

                    if (line.Length > 0)
                    {
                        int index = 0;
                        // Loop over all commas in line
                        while ((index = line.IndexOf(',', index)) != -1)
                        {
                            int spaceIndex = index + 1;
                            // Determine how many spaces after comma
                            while (spaceIndex < line.Length && line[spaceIndex] == ' ')
                            {
                                ++spaceIndex;
                            }

                            int      spaceCount      = spaceIndex - (index + 1);
                            string   replacementText = " ";
                            bool     fDoEdit         = true;
                            TextSpan editTextSpan    = new TextSpan();

                            editTextSpan.iStartLine  = i;
                            editTextSpan.iEndLine    = i;
                            editTextSpan.iStartIndex = index + 1;

                            if (spaceIndex == line.Length)
                            {
                                if (spaceCount > 0)
                                {
                                    // Delete spaces after a comma at end of line
                                    editTextSpan.iEndIndex = spaceIndex;
                                    replacementText = "";
                                }
                                else
                                {
                                    // Otherwise, do not add spaces if comma is
                                    // at end of line.
                                    fDoEdit = false;
                                }
                            }
                            else if (spaceCount == 0)
                            {
                                if (spaceIndex < line.Length && line[spaceIndex] == '\t')
                                {
                                    // Do not insert space if a tab follows
                                    // a comma.
                                    fDoEdit = false;
                                }
                                else
                                {
                                    // No space after comma so add a space.
                                    editTextSpan.iEndIndex = index + 1;
                                }
                            }
                            else if (spaceCount > 1)
                            {
                                // More than one space after comma, replace
                                // with a single space.
                                editTextSpan.iEndIndex = spaceIndex;
                            }
                            else
                            {
                                // Single space after a comma and not at end
                                // of the line, leave it alone.
                                fDoEdit = false;
                            }
                            if (fDoEdit)
                            {
                                // Add edit operation
                                mgr.Add(new EditSpan(editTextSpan, replacementText));
                            }
                            index = spaceIndex;
                        }
                    }
                    startIndex = 0; // All subsequent lines start at 0
                }
                // Apply all edits
                mgr.ApplyEdits();
            }
        }
    }
}
```

## <a name="using-the-compoundaction-class"></a>Použití třídy CompoundAction

Všechna přeformátování provedené u oddílu kódu by měla být v rámci jedné akce vratná. To lze provést pomocí <xref:Microsoft.VisualStudio.Package.CompoundAction> třídy. Tato třída zalomí sadu operací úprav pro textovou vyrovnávací paměť do jediné operace Edit.

### <a name="example"></a>Příklad

Zde je příklad použití třídy <xref:Microsoft.VisualStudio.Package.CompoundAction>. Příklad metody `DoFormatting` naleznete v části "implementace podpory pro formátování" v tomto tématu.

```csharp
using Microsoft.VisualStudio.Package;
using Microsoft VisualStudio.TextManager.Interop;

namespace MyLanguagePackage
{
    class MySource : Source
    {
        public override void ReformatSpan(EditArray mgr, TextSpan span)
        {
            string description = "Reformat code";
            CompoundAction ca = new CompoundAction(this, description);
            using (ca)
            {
                ca.FlushEditActions();      // Flush any pending edits
                DoFormatting(mgr, span);    // Format the span
            }
        }
    }
}
```

## <a name="see-also"></a>Viz také:

- [Funkce služby starší verze jazyka](legacy-language-service-features1.md)