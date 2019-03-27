---
title: Množiny pravidel analýzy kódu
ms.date: 04/02/2018
ms.topic: conceptual
f1_keywords:
- vs.codeanalysis.rulesets.learnmore
helpviewer_keywords:
- code analysis, rule sets
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c95b442835289265d197b6806c6d87fa051f2c1b
ms.sourcegitcommit: d78821f8c353e0102b1554719f549f32dffac71b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/27/2019
ms.locfileid: "58515230"
---
# <a name="use-rule-sets-to-group-code-analysis-rules"></a>Použití sady pravidel k seskupování pravidel analýzy kódu

Při konfiguraci analýzy kódu v sadě Visual Studio, můžete zvolit ze seznamu předdefinovaných *sad pravidel*. Sada pravidel je seskupení pravidel analýzy kódu, které vyhledávají cílené problémy a zvláštní podmínky pro daný projekt. Například můžete použít sadu pravidel, která je navržená k vyhledání kódu veřejně dostupných rozhraní API. Můžete také použít sadu pravidel, která zahrnuje všechna dostupná pravidla.

Můžete přizpůsobit sadu přidáním nebo odstraněním pravidel nebo změnou pravidel závažnosti jako upozornění nebo chyby v pravidel **seznam chyb**. Sada vlastních pravidel může splnit potřebu konkrétního vývojového prostředí. Při přizpůsobování sady pravidel obsahuje editor sad pravidel vyhledávání a filtrování nástroje, které vám proces usnadní.

Sady pravidel jsou k dispozici pro [statické analýzy spravovaného kódu](how-to-configure-code-analysis-for-a-managed-code-project.md), [analýzu kódu C++](using-rule-sets-to-specify-the-cpp-rules-to-run.md), a [analyzátory Roslyn](analyzer-rule-sets.md).

## <a name="rule-set-format"></a>Sada pravidel formátu

Sada pravidel je zadaný ve formátu XML *.ruleset* souboru. Pravidla, která se skládá z ID a *akce*, jsou seskupené podle ID analyzátoru a obor názvů v souboru.

Obsah *.ruleset* vypadá podobně jako tato konfigurace XML souboru:

```xml
<RuleSet Name="Rules for Hello World project" Description="These rules focus on critical issues for the Hello World app." ToolsVersion="10.0">
  <Localization ResourceAssembly="Microsoft.VisualStudio.CodeAnalysis.RuleSets.Strings.dll" ResourceBaseName="Microsoft.VisualStudio.CodeAnalysis.RuleSets.Strings.Localized">
    <Name Resource="HelloWorldRules_Name" />
    <Description Resource="HelloWorldRules_Description" />
  </Localization>
  <Rules AnalyzerId="Microsoft.Analyzers.ManagedCodeAnalysis" RuleNamespace="Microsoft.Rules.Managed">
    <Rule Id="CA1001" Action="Warning" />
    <Rule Id="CA1009" Action="Warning" />
    <Rule Id="CA1016" Action="Warning" />
    <Rule Id="CA1033" Action="Warning" />
  </Rules>
  <Rules AnalyzerId="Microsoft.CodeQuality.Analyzers" RuleNamespace="Microsoft.CodeQuality.Analyzers">
    <Rule Id="CA1802" Action="Error" />
    <Rule Id="CA1814" Action="Info" />
    <Rule Id="CA1823" Action="None" />
    <Rule Id="CA2217" Action="Warning" />
  </Rules>
</RuleSet>
```

> [!TIP]
> Je snazší [upravit sadu pravidel](../code-quality/working-in-the-code-analysis-rule-set-editor.md) v grafickém **editoru nastavte pravidlo** než ručně.

## <a name="specify-a-rule-set-for-a-project"></a>Zadejte sadu pravidel pro projekt

Pravidlo nastavené pro projekt je určená **CodeAnalysisRuleSet** vlastnost v souboru projektu sady Visual Studio. Příklad:

```xml
<PropertyGroup Condition=" '$(Configuration)|$(Platform)' == 'Debug|AnyCPU' ">
  ...
  <CodeAnalysisRuleSet>HelloWorld.ruleset</CodeAnalysisRuleSet>
</PropertyGroup>
```

## <a name="see-also"></a>Viz také:

- [Referenční dokumentace sady pravidel nástroje Analýza kódu](../code-quality/rule-set-reference.md)