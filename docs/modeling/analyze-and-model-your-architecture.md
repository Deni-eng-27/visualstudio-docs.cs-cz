---
title: Analýza a modelování vaší architektury
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.topic: conceptual
helpviewer_keywords:
- Visual Studio Ultimate, exploring code
- Visual Studio Ultimate, visualizing code
- diagrams - modeling
- Visual Studio ALM, modeling
- application, design
- architecture
- code visualization
- application design
- applications, architecture
- code exploration
- Visual Studio ALM, exploring code
- modeling
- application architecture
- application, modeling
- applications, modeling
- architecture [Visual Studio ALM], modeling
- application modeling
- Visual Studio Ultimate, modeling
- architecture [Visual Studio Ultimate], modeling
- application, architecture
- Visual Studio ALM, visualizing code
- applications, designing
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: be58a86ec6c3b87954ff5b5be012ce636ad52204
ms.sourcegitcommit: 56018fb1f52f17bf35ae2ce71c50c763486e6173
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/04/2018
ms.locfileid: "33106957"
---
# <a name="analyze-and-model-your-architecture"></a>Analýza a modelování vaší architektury
Ujistěte se, že vaše aplikace splňuje požadavky architektury pomocí sady Visual Studio architektura a modelování nástroje pro návrh a modelování vaší aplikace.

* Snadněji Pochopte stávající kód programu pomocí sady Visual Studio k vizualizaci struktury, chování a vztahy kódu.

* Informujte váš tým potřebu respektováním architektury závislosti.

* Vytváření modelů na různých úrovních podrobností v průběhu životního cyklu aplikací v rámci vývojových procesech.

V tématu [scénář: Změna návrhu pomocí vizualizace a modelování](../modeling/scenario-change-your-design-using-visualization-and-modeling.md).

## <a name="to"></a>Chcete-li

|||
|-|-|
|**Vizualizace kódu**:<br /><br /> – Zobrazí organizace a vztahy kódu vytvořením map kódu. Vizualizace závislosti mezi sestavení, obory názvů, třídy, metod a tak dále.<br />– Zobrazí struktura třídy a členy pro konkrétní projekt tak, že vytvoříte diagramů tříd z kódu.<br />-Vyhledání konflikty mezi váš kód a jeho návrhu vytvořením závislostí diagramy ověření kódu.|-   [Vizualizace kódu](../modeling/visualize-code.md)<br />-   [Práce s třídami a ostatními typy (návrhář tříd)](../ide/working-with-classes-and-other-types-class-designer.md)<br />-   [Video: Porozumět návrhu z kódu pomocí sady Visual Studio 2015 mapy kódu](https://channel9.msdn.com/Events/Visual-Studio/Connect-event-2015/502)<br />-   [Video: Ověření svoje závislosti architektury v reálném čase](https://sec.ch9.ms/sessions/69613110-c334-4f25-bb36-08e5a93456b5/170ValidateArchitectureDependenciesWithVisualStudio.mp4)|
|**Definování architekturu**:<br /><br /> -Definovat a vynutit omezení závislosti mezi součástmi kódu tak, že vytvoříte diagramy závislostí.|-   [Video: Ověření závislosti architektury pomocí sady Visual Studio (Channel 9)](https://channel9.msdn.com/Events/Connect/2016/170)|
|**Ověřování systému s požadavky a určen návrhu:**<br /><br /> -Ověření závislostem kódu pomocí diagramů závislostí, které popisují určený architekturu a zabránit změny, které může být v konfliktu s návrhu.|-   [Video: Ověření závislosti architektury pomocí sady Visual Studio (Channel 9)](https://channel9.msdn.com/Events/Connect/2016/170)|
|**Přizpůsobení modelů a diagramů**:<br /><br /> -Vytvořte vlastní jazyky specifické pro doménu.|-   [Modelování SDK pro Visual Studio – specifické pro doménu jazyky](../modeling/modeling-sdk-for-visual-studio-domain-specific-languages.md)|
|**Generování textu s použitím šablon T4**:<br /><br /> -Použít text bloky a logiku řízení uvnitř šablony pro vygenerování souborů založený na textu.<br /> – T4 šablony sestavení pomocí nástroje MSBuild zahrnuté v sadě Visual Studio|-   [Generování kódu a textové šablony T4](../modeling/code-generation-and-t4-text-templates.md)|
|**Sdílení modelů, diagramy a map kódu pomocí správy verzí Team Foundation**:<br /><br /> -Uveďte map kódu, projektů a diagramů závislosti v rámci správy verzí Team Foundation v, můžete je sdílet.| |

Informace, které verze sady Visual Studio podporují jednotlivé funkce, najdete v tématu [verze podpora architektura a modelování nástroje](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport)

## <a name="types-of-models-and-typical-uses"></a>Typy modely a typické použití

### <a name="code-maps"></a>Mapy kódu
Kód mapuje nápovědy zobrazí organizace a vztahy do vašeho kódu.

**Typické použití:**

-   Kontrola kódu programu, můžete lépe pochopit jeho strukturu a jeho závislé součásti, aktualizujte a odhadnout náklady na navrhované změny.

**Přejděte na téma:**

-   [Mapování závislostí napříč vaším řešením](../modeling/map-dependencies-across-your-solutions.md)
-   [Použití map kódu k ladění aplikací](../modeling/use-code-maps-to-debug-your-applications.md)
-   [Nalezení potenciálních problémů pomocí analyzátorů mapy kódu](../modeling/find-potential-problems-using-code-map-analyzers.md)

### <a name="dependency-diagram"></a>Diagram závislostí
Diagramy závislostí umožňují definovat strukturu aplikace jako sada vrstvy nebo je blokuje explicitní závislosti. Můžete spustit ověření ke zjištění konfliktu mezi závislosti v kódu a závislosti, které jsou popsané v diagramu závislostí.

**Typické použití:**

-   Struktura aplikace prostřednictvím celá řada změn stabilizaci průběhu své životnosti.
-   Zjišťování konfliktů neúmyslnému závislostí před vrácením se změnami změny kódu.

**Přejděte na téma:**

-   [Vytváření diagramů závislostí z kódu](../modeling/create-layer-diagrams-from-your-code.md)
-   [Diagramy závislostí: Referenční dokumentace](../modeling/layer-diagrams-reference.md)
-   [Ověřování kódu pomocí diagramů závislostí](../modeling/validate-code-with-layer-diagrams.md)

### <a name="domain-specific-language-dsl"></a>Jazyk specifické pro doménu (DSL)
DSL je zápis, který návrh pro konkrétní účel. V sadě Visual Studio je obvykle grafického rozhraní.

**Typické použití:**

-   Generovat nebo nakonfigurujte částí aplikace. Práce se vyžaduje vyvíjet zápis a nástroje. Výsledkem mohou být lépe odpovídaly k vaší doméně než UML přizpůsobení.
-   U velkých projektů nebo řádky produktů, kde je velikost investice do vývoje DSL a jeho nástroje vrácený jeho použití v více než jeden projekt.

**Přejděte na téma:**

-   [Sada Modeling SDK pro Visual Studio – jazyky specifické pro doménu](../modeling/modeling-sdk-for-visual-studio-domain-specific-languages.md)

## <a name="where-can-i-get-more-information"></a>Kde lze získat další informace?

[Visual Studio vizualizace & modelování fóra nástroje](http://go.microsoft.com/fwlink/?LinkId=184720)

## <a name="see-also"></a>Viz také

- [Co je nového](../modeling/what-s-new-for-design-in-visual-studio.md)
- [Správa životního cyklu aplikací DevOps a](http://msdn.microsoft.com/Library/74a1f71d-7f23-4c71-8fd7-89ede614fab6)
