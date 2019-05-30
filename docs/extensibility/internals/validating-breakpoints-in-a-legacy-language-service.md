---
title: Ověřování zarážek ve službě starší verze jazyka | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- breakpoint validation
- language services [managed package framework], breakpoint validation
ms.assetid: a7e873cd-dfe1-474f-bda5-fd7532774b15
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 177b0bb3fddebab6518a851bf8ce4c4d34d43897
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66324565"
---
# <a name="validating-breakpoints-in-a-legacy-language-service"></a>Ověřování zarážek ve službě starší verze jazyka
Zarážky označuje, že spuštění programu by se měla zastavit v určitém místě, když je spuštěn v ladicí program. Uživatele můžete umístit zarážky na kterýkoli řádek v ve zdrojovém souboru, protože nemá žádné informace o tom, co platné umístění zarážky editoru. Když ladicí program se spustí, všechny označené zarážky (označované jako čekajících zarážek) jsou vázány na příslušné umístění v běžící aplikaci. Ve stejnou dobu, kterou zarážek se ověří a zkontrolujte, že se označení umístění platný kód. Například zarážky na komentář není platný, protože není na tomto místě ve zdrojovém kódu žádný kód. Ladicí program se zakáže neplatný zarážky.

 Protože služba jazyka ví o zdrojovém kódu se zobrazí, předtím, než se spustí ladicí program může ověřit zarážky. Je možné přepsat <xref:Microsoft.VisualStudio.Package.LanguageService.ValidateBreakpointLocation%2A> metoda vrátí rozpětí určující platné umístění zarážky. Umístění zarážky stále ověření při spuštění ladicího programu, ale uživatel je informován o neplatný zarážky bez čekání na ladicí program načíst.

## <a name="implementing-support-for-validating-breakpoints"></a>Implementace podporu pro ověřování zarážek

- <xref:Microsoft.VisualStudio.Package.LanguageService.ValidateBreakpointLocation%2A> Metoda je uvedena umístění zarážky. Implementace musíte rozhodnout, zda je platná umístění a označující, že to tak, že vrací rozpětí textu, který identifikuje kód přidružený k řádku pozici zarážku.

- Vrátí <xref:Microsoft.VisualStudio.VSConstants.S_OK> Pokud je toto umístění platné, nebo <xref:Microsoft.VisualStudio.VSConstants.S_FALSE> Pokud není platná.

- Pokud zarážka je platný rozsah textu je zvýrazněn spolu s zarážku.

- Pokud zarážka není platná, zobrazí se chybová zpráva ve stavovém řádku.

### <a name="example"></a>Příklad
 Tento příklad ukazuje implementaci <xref:Microsoft.VisualStudio.Package.LanguageService.ValidateBreakpointLocation%2A> metodu, která volá analyzátor, který má získat délka kódu (pokud existuje) v zadaném umístění.

 Tento příklad předpokládá, že jste přidali `GetCodeSpan` metodu <xref:Microsoft.VisualStudio.Package.AuthoringSink> třídu, která ověřuje text rozpětí a vrátí `true` Pokud se jedná o platný zarážku umístění.

```csharp
using Microsoft VisualStudio;
using Microsoft.VisualStudio.Package;
using Microsoft.VisualStudio.TextManager.Interop;

namespace TestLanguagePackage
{
    class TestLanguageService : LanguageService
    {
        public override int ValidateBreakpointLocation(IVsTextBuffer buffer,
                                                       int line,
                                                       int col,
                                                       TextSpan[] pCodeSpan)
        {
            int retval = VSConstants.S_FALSE;
            if (pCodeSpan != null)
            {
                // Initialize span to current line by default.
                pCodeSpan[0].iStartLine = line;
                pCodeSpan[0].iStartIndex = col;
                pCodeSpan[0].iEndLine = line;
                pCodeSpan[0].iEndIndex = col;
            }

            if (buffer != null)
            {
                IVsTextLines textLines = buffer as IVsTextLines;
                if (textLines != null)
                {
                    Source src = this.GetSource(textLines);
                    if (src != null)
                    {
                        TokenInfo tokenInfo = new TokenInfo();
                        string text = src.GetText();
                        ParseRequest req = CreateParseRequest(src,
                                                              line,
                                                              col,
                                                              tokenInfo,
                                                              text,
                                                              src.GetFilePath(),
                                                              ParseReason.CodeSpan,
                                                              null);
                        req.Scope = this.ParseSource(req);
                        TestAuthoringSink sink = req.Sink as TestAuthoringSink;

                        TextSpan span = new TextSpan();
                        if (sink.GetCodeSpan(out span))
                        {
                            pCodeSpan[0] = span;
                            retval = VSConstants.S_OK;
                        }
                    }
                }
            }
            return retval;
        }
    }
}
```

## <a name="see-also"></a>Viz také
- [Funkce služby starší verze jazyka](../../extensibility/internals/legacy-language-service-features1.md)