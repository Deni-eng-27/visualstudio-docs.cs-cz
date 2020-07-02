---
title: Vizualizovat kód | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
helpviewer_keywords:
- code, understanding
- code, visualizing
- code, exploring
ms.assetid: 0dd7d438-393a-4cd3-b417-9bf37379e1b0
caps.latest.revision: 49
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 665dc76126eac964f405be06605c40b5b30cc9a5
ms.sourcegitcommit: b885f26e015d03eafe7c885040644a52bb071fae
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/30/2020
ms.locfileid: "85532935"
---
# <a name="visualize-code"></a>Vizualizace kódu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Pomocí nástrojů pro vizualizaci a modelování v aplikaci Visual Studio můžete pochopit existující kód a popsat svou aplikaci. To vám umožní vizuálně zjistit, jak změny můžou ovlivnit kód, a pomohou vám posoudit práci a rizika vyplývající z těchto změn. Příklad:

- Chcete-li pochopit vztahy v kódu, namapujte tyto vztahy vizuálně.

- K popisu architektury systému a udržování kódu v souladu s návrhem, vytváření diagramů vrstev a ověřování kódu proti těmto diagramům.

- Chcete-li popsat struktury tříd, vytvořte diagramy tříd.

- Pokud chcete modelovat a komunikovat s různými aspekty systému, nakreslete jazyk UML (Unified Modeling Language) (UML) diagramy. Můžete například modelovat součásti systému, typy, interakce a procesy.

  Tyto nástroje také usnadňují komunikaci s lidmi, které se podílejí na vašem projektu. Diagramy tříd UML můžete například použít k vytvoření společného glosáře pro diskuzi systému se zúčastněnými stranami projektu, uživateli a členy týmu.

  Chcete-li zjistit, které verze aplikace Visual Studio podporují jednotlivé funkce, přečtěte si téma [podpora verzí pro nástroje pro architekturu a modelování](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport)

## <a name="what-do-you-want-to-do"></a>Co chcete udělat?

|Scénář|Články|
|-|-|
|**Pochopení kódu a jeho vztahů:**<br /><br /> Mapování vztahů mezi určitými částmi kódu.<br /><br /> Podívejte se na přehled vztahů v kódu pro celé řešení.<br /><br /> **Poznámka**: v této verzi sady Visual Studio se jako místo *grafu závislostí*používá pojem *Mapa kódu* .|-   [Mapování závislostí napříč vašimi řešeními](../modeling/map-dependencies-across-your-solutions.md)<br />-   [Použití map kódu k ladění aplikací](../modeling/use-code-maps-to-debug-your-applications.md)<br />-   [Nalezení potenciálních problémů pomocí analyzátorů mapy kódu](../modeling/find-potential-problems-using-code-map-analyzers.md)<br />-   [Mapování metod v zásobníku volání při ladění](../debugger/map-methods-on-the-call-stack-while-debugging-in-visual-studio.md)|
|**Porozumění strukturám tříd:**<br /><br /> Vizualizujte strukturu tříd v projektu vytvořením diagramů tříd z kódu.|[Postupy: Přidání diagramů tříd do projektů (Návrhář tříd)](../ide/how-to-add-class-diagrams-to-projects-class-designer.md)|
|**Popište návrh systému vysoké úrovně a ověřte kód pro tento návrh:**<br /><br /> Popište návrh systému vysoké úrovně a jeho zamýšlené závislosti vytvořením diagramů vrstev. Ověřte kód pro tento návrh a ujistěte se, že závislosti v kódu zůstávají v souladu s návrhem.|-   [Vytváření diagramů vrstev z kódu](../modeling/create-layer-diagrams-from-your-code.md)<br />-   [Diagramy vrstev: Referenční dokumentace](../modeling/layer-diagrams-reference.md)<br />-   [Diagramy vrstev: pokyny](../modeling/layer-diagrams-guidelines.md)<br />-   [Ověřování kódu pomocí diagramů vrstev](../modeling/validate-code-with-layer-diagrams.md)|
|**Komunikace s požadavky a architekturou uživatele:**<br /><br /> Vykreslením následujících diagramů UML můžete modelovat požadavky uživatelů a architekturu softwarového systému: aktivita, komponenta, třída, sekvence a případ použití.|-   [Vytváření modelů pro aplikaci](../modeling/create-models-for-your-app.md)<br />-   [Modelování uživatelských požadavků](../modeling/model-user-requirements.md)<br />-   [Modelování architektury aplikace](../modeling/model-your-app-s-architecture.md)|

## <a name="external-resources"></a>Externí zdroje

|**Kategorie**|**Odkazy**|
|------------------|---------------|
|**Fóra**|-   [Nástroje pro vizualizaci sady Visual Studio & modelování](https://social.msdn.microsoft.com/Forums/en-US/home?forum=vsarch)<br />-   [Sada Visual Studio vizualizace & Modeling SDK (nástroje DSL)](https://social.msdn.microsoft.com/Forums/home?forum=dslvsarchx)|
|**Blogy**|[Blog sady Visual Studio ALM + Team Foundation Server](https://devblogs.microsoft.com/devops/welcome-to-the-visual-studio-alm-team-foundation-server-blog/)|
|**Technické články a deníky**|[Fórum architektury MSDN](https://msdn.microsoft.com/architecture/default.aspx)|

## <a name="see-also"></a>Viz také
 [Scénář: Změna návrhu pomocí vizualizace a modelování](../modeling/scenario-change-your-design-using-visualization-and-modeling.md) [analýzy a modelování](../modeling/analyze-and-model-your-architecture.md) [vytváření modelů pro](../modeling/create-models-for-your-app.md) model [požadavků na uživatele](../modeling/model-user-requirements.md) modelu [vaší](../modeling/model-your-app-s-architecture.md) aplikace [použití modelů v procesu vývoje](../modeling/use-models-in-your-development-process.md)
