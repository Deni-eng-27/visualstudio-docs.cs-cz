---
title: Návrhář postupu provádění – Návrhář aktivity v vývojovém diagramu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Statements.Flowchart.UI
- System.Activities.Statements.FlowStep.UI
- System.Activities.Core.Presentation.FlowStart.UI
ms.assetid: d5af2276-5215-4138-880a-cf2b90bbf3a0
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 5f56c7eac56572d8a3be1f8b478feb0543390481
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/19/2019
ms.locfileid: "72650460"
---
# <a name="flowchart-activity-designer"></a>Návrhář aktivity Flowchart

Aktivita <xref:System.Activities.Statements.Flowchart> slouží k vytváření pracovních postupů, které definují a spravují složité ovládací prvky toku. @No__t_0 lze vytvořit buď v kódu, nebo pomocí Návrhář postupu provádění. Toto téma popisuje prostředí Návrhář postupu provádění. Návrhář aktivity pracovního postupu Návrhář postupu provádění umožňuje vývojářům přirozeným způsobem vytvářet pracovní postupy.

## <a name="the-flowchart-activity"></a>Aktivita vývojového diagramu

@No__t_0 Určuje jedinečný <xref:System.Activities.Statements.Flowchart.StartNode%2A>, který se spustí při spuštění pracovního postupu, a používá síť propojených <xref:System.Activities.Statements.Flowchart.Nodes%2A> k vytvoření libovolných smyček nebo k překonání toku provádění na kdekoli jinde v pracovním postupu v daném čase.

### <a name="using-the-flowchart-activity-designer"></a>Pomocí návrháře aktivit vývojového diagramu

Návrhář aktivity **vývojového diagramu** se dá najít v kategorii **vývojové diagramy** na **panelu nástrojů**, ke které se dostanete kliknutím na kartu **panelu nástrojů** na Návrhář postupu provádění. Případně vyberte v nabídce **zobrazení** možnost **Sada nástrojů** nebo stiskněte klávesovou **zkratku CTRL** +**ALT** +**X**.

Návrhář aktivity **vývojového diagramu** lze přetáhnout ze **sady nástrojů** a přetáhnout na Návrhář postupu provádění plochu všude, kde se normálně umísťují návrháři aktivit, a to buď jako kořenovou aktivitu, nebo jako podřízenou položku jiné aktivity toku řízení. Pokud je Návrhář aktivity **vývojového diagramu** na prázdné Návrhář postupu provádění povrchu, vytvoří aktivitu <xref:System.Activities.Statements.Flowchart>, která se ve výchozím nastavení projeví v rozšířeném zobrazení, ve kterém je počáteční uzel, který iniciuje spuštění, reprezentován zelenou kuličkou. Pokud je Návrhář aktivity **vývojového diagramu** vyřazen do jiné aktivity toku řízení, zobrazí se v minimalizovaném zobrazení, které lze rozšířit dvojitým kliknutím na Návrhář aktivity **vývojového diagramu** . Jakékoli aktivity v **sadě nástrojů** lze přetáhnout přímo do návrháře aktivit **vývojového diagramu** , včetně dalších aktivit toku řízení.

Po přetahování různých návrhářů aktivit na plátno Návrhář postupu provádění lze objekty <xref:System.Activities.Activity>, které představují, propojit dohromady a určit pořadí spouštění. Chcete-li vytvořit propojení mezi zdrojovou aktivitou a cílovou aktivitou, na každé straně se zobrazí ukazatel myši nad návrhářem zdrojové aktivity a čtvercových popisovačů. Klikněte na jeden z čtvercových popisovačů a přetáhněte ho podržením tlačítka myši na jeden z úchytů, který se zobrazí podobným způsobem kolem cílové aktivity při umístění ukazatele myši myší. Uvolněte tlačítko myši a vytvoří se propojení mezi dvěma aktivitami, které jsou reprezentovány jako šipka od návrháře zdrojového kódu do cílového návrháře.

### <a name="flowchart-activity-properties"></a>Vlastnosti aktivity vývojového diagramu

V následující tabulce jsou uvedeny vlastnosti <xref:System.Activities.Statements.Flowchart> a popisuje, jak se používají v návrháři. Tyto vlastnosti lze upravovat v mřížce vlastností nebo na návrhové ploše.

|Název vlastnosti|Požadováno|Použití|
|-|--------------|-|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Určuje zobrazovaný název návrháře aktivit v hlavičce. Výchozí hodnota je vývojový diagram. Hodnotu lze upravit v okně **vlastnosti** nebo přímo v hlavičce návrháře aktivit.<br /><br /> I když <xref:System.Activities.Activity.DisplayName%2A> není nezbytně nutné, je osvědčeným postupem použití jednoho.|
|<xref:System.Activities.Statements.Flowchart.Variables%2A>|False|Kolekce proměnných, které jsou vymezeny v rámci této <xref:System.Activities.Statements.Flowchart> ke sdílení stavu napříč svými podřízenými aktivitami.|
|<xref:System.Activities.Statements.Flowchart.StartNode%2A>|False|@No__t_0, která se spustí při spuštění <xref:System.Activities.Statements.Flowchart>|
|<xref:System.Activities.Statements.Flowchart.Nodes%2A>|False|Obsahuje kolekci objektů <xref:System.Activities.Statements.FlowNode> v <xref:System.Activities.Statements.Flowchart>.|

## <a name="see-also"></a>Viz také:

- [Vývojový diagram](../workflow-designer/flowchart-activity-designers.md)
- [FlowDecision](../workflow-designer/flowdecision-activity-designer.md)
- [FlowSwitch\<T>](../workflow-designer/flowswitch-t-activity-designer.md)