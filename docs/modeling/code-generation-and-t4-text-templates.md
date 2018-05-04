---
title: Vytvoření kódu a textové šablony T4
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.TextTemplating.TextTemplating
helpviewer_keywords:
- generating text
- .tt files
- code generation
- text templates
- generating code
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2f4fed2cbf00717e4eaf9c1353370dbd96037491
ms.sourcegitcommit: a8e01952be5a539104e2c599e9b8945322118055
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/03/2018
---
# <a name="code-generation-and-t4-text-templates"></a>Vytvoření kódu a textové šablony T4

V sadě Visual Studio *textové šablony T4* je směs text bloky a řízení logiky, která může generovat textového souboru. Ovládací prvek logiku je zapsána jako fragmenty kódu programu [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] nebo [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]. V sadě Visual Studio 2015 Update 2 nebo novější můžete v šablonách T4 – direktivy jazyka C# – funkce verze 6.0. Vygenerovaný soubor může být text libovolného typu, například webovou stránku nebo soubor prostředků nebo zdrojový kód aplikace v libovolném jazyce.

Existují dva typy textových šablon T4: Spusťte čas a v době návrhu.

## <a name="run-time-t4-text-templates"></a>Textové šablony T4 čas spuštění

Také označované jako 'předběžně zpracované, šablon, spusťte čas šablony jsou spouštěny v aplikaci k vytvoření textového řetězce, obvykle v rámci jeho výstup. Můžete například vytvořit šablonu definovat stránku HTML:

```
<html><body>
 The date and time now is: <#= DateTime.Now #>
</body></html>
```

Všimněte si, že šablona podobá generovaný výstup. Podobnosti šablonu, kterou chcete výsledný výstup umožňuje vyhnout se chybám, pokud chcete změnit.

Kromě toho obsahuje šablony fragmentů kódu programu. Můžete tyto fragmenty opakování části textu, aby podmíněného části a zobrazte data z vaší aplikace.

Generovat výstup, aplikace volá funkci, která je generován šablony. Příklad:

```csharp
string webResponseText = new MyTemplate().TransformText();
```

Aplikaci můžete spustit na počítači, který nemá nainstalovanou sadu Visual Studio.

Chcete-li vytvořit šablonu spuštění, přidejte **Preprocessed textové šablony** souboru do projektu. Alternativně můžete přidat soubor ve formátu prostého textu a nastavit jeho **Custom Tool** vlastnost **texttemplatingfilepreprocessor –**.

Další informace najdete v tématu [generování textu běhu pomocí textových šablon T4](../modeling/run-time-text-generation-with-t4-text-templates.md). Další informace o syntaxi šablony najdete v tématu [zápis textové šablony T4](../modeling/writing-a-t4-text-template.md).

## <a name="design-time-t4-text-templates"></a>Návrh textových šablon T4 čas

Návrh čas tempaltes definovat součástí zdrojového kódu a dalším prostředkům vaší aplikace. Obvykle použijete několik šablon, které číst data v jednom vstupního souboru nebo databáze a generovat některé z vaší *.cs*, *VB*, nebo jiné zdrojové soubory. Každá šablona generuje jeden soubor. Jsou prováděna v sadě Visual Studio nebo MSBuild.

Soubor XML konfiguračních dat může být například vstupní data. Vždy, když chcete upravit soubor XML při vývoji, znovu vygenerujte textové šablony součástí kódu aplikace. Jednu z šablon může podobat následujícímu příkladu:

```
<#@ output extension=".cs" #>
<#@ assembly name="System.Xml" #>
<#
 System.Xml.XmlDocument configurationData = ...; // Read a data file here.
#>
namespace Fabrikam.<#= configurationData.SelectSingleNode("jobName").Value #>
{
  ... // More code here.
}
```

V závislosti na hodnoty v souboru XML, vygenerovaného *.cs* soubor bude vypadat takto:

```
namespace Fabrikam.FirstJob
{
  ... // More code here.
}
```

Například může být vstup diagram pracovního postupu v obchodní aktivity. Pokud uživatelé změnit jejich pracovní postup společnosti, nebo když spustíte pracovní s nových uživatelů, kteří mají jiný pracovní postup, je snadné se znova vygenerovat kód podle nový model.

Návrh šablony umožňují rychlejší a spolehlivější a změňte konfiguraci při změně požadavky. Vstup je obvykle definovány z hlediska obchodní požadavky, jako v příkladu pracovního postupu. To usnadňuje popisují změny s uživateli. Návrh šablony jsou proto užitečným nástrojem v procesu agile vývoj.

Chcete-li vytvořit šablonu návrhu, přidejte **textové šablony** souboru do projektu. Alternativně můžete přidat soubor ve formátu prostého textu a nastavit jeho **Custom Tool** vlastnost **TextTemplatingFileGenerator**.

Další informace najdete v tématu [vytvoření kódu v době návrhu pomocí textových šablon T4](../modeling/design-time-code-generation-by-using-t4-text-templates.md). Další informace o syntaxi šablony najdete v tématu [zápis textové šablony T4](../modeling/writing-a-t4-text-template.md).

> [!NOTE]
> Termín *modelu* se někdy používá k popisu jednu nebo více šablon číst data. Model může být v libovolném formátu v libovolného typu souboru nebo databáze. Nemá být modelu UML nebo model jazyka domény. 'Model' právě označuje, že data může být definována v podmínkách obchodní koncepty, nikoli tvaru kód.

Funkce transformace textových šablon jmenuje *T4*.

## <a name="see-also"></a>Viz také

- [Vytváření kódu z jazyka specifického pro doménu](../modeling/generating-code-from-a-domain-specific-language.md)