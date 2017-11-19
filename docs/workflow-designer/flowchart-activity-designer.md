---
title: "Vývojový diagram Návrhář aktivity | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- System.Activities.Statements.Flowchart.UI
- System.Activities.Statements.FlowStep.UI
- System.Activities.Core.Presentation.FlowStart.UI
ms.assetid: d5af2276-5215-4138-880a-cf2b90bbf3a0
caps.latest.revision: "5"
author: ErikRe
ms.author: erikre
manager: erikre
ms.openlocfilehash: 738568db51cce97ee0b110220aa195b4ded2adba
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="flowchart-activity-designer"></a>Vývojový diagram Návrhář aktivity
<xref:System.Activities.Statements.Flowchart> Aktivita se používá k vytváření pracovních postupů, které definovat a spravovat komplexní tok ovládací prvky. A <xref:System.Activities.Statements.Flowchart> může být vytvořené v kódu nebo pomocí [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]. Toto téma dokumenty [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] prostředí. [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)] Návrhář aktivity pracovního postupu umožňuje vývojářům pro vytváření pracovních postupů přirozené způsobem.  
  
## <a name="the-flowchart-activity"></a>Vývojový diagram aktivity  
 <xref:System.Activities.Statements.Flowchart> Určuje jedinečný <xref:System.Activities.Statements.Flowchart.StartNode%2A> který se spustí při spuštění pracovního postupu a používá síť propojení <xref:System.Activities.Statements.Flowchart.Nodes%2A> můžete vytvořit libovolný smyčky nebo přesměrovat tok na kdekoliv jinde v pracovním postupu provedení v daném okamžiku.  
  
### <a name="using-the-flowchart-activity-designer"></a>Pomocí návrháře vývojový diagram aktivity  
 **Vývojový diagram** Návrhář aktivity naleznete v **vývojový diagram** kategorii **sada nástrojů**, který přistupuje kliknutím **sady nástrojů**na kartě [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] (případně vyberte možnost **nástrojů** z **zobrazení** nabídky nebo CTRL + ALT + X.)  
  
 **Vývojový diagram** Návrhář aktivity můžete přetáhnout z **sada nástrojů** a vynechaných na [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] prostor kdekoli návrháře aktivit jsou obvykle umístěny, jako kořenové aktivity nebo jako podřízený objekt jiné aktivity toku řízení. Pokud **vývojový diagram** Návrhář aktivity umístění na prázdné pole [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] prostor, vytvoří <xref:System.Activities.Statements.Flowchart> aktivity, který ve výchozím nastavení prezentuje v rozbalené zobrazení, ve kterém je počáteční uzel, který iniciuje provádění reprezentován jako zelená míč. Pokud **vývojový diagram** Návrhář aktivity je vyřazeno do další aktivity toku řízení, se prezentuje v minimalizovaném okně zobrazení, které lze rozšířit dvojitým kliknutím **vývojový diagram** Návrhář aktivity. Všechny aktivity v **sada nástrojů** může být přetažen přímo na **vývojový diagram** Návrhář aktivity, včetně další aktivity toku řízení.  
  
 Po přetahování různé návrháře aktivit do [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] plátno, <xref:System.Activities.Activity> lze propojit objekty, které představují společně k určení pořadí zpracování. Pokud chcete vytvořit vazbu mezi aktivitou zdrojové a cílové aktivitě, myši nad návrháře zdrojové aktivity a odmocnina obslužné rutiny zobrazí na každé straně je. Klikněte na jednu z odmocnina obslužné rutiny a přetáhněte jej podržte tlačítko myši na jednu z obslužných rutin, které se zobrazí podobným způsobem kolem cílová aktivita, když ukazatele myši ho pomocí myši. Uvolnění tlačítka myši a vytvoří propojení mezi tyto dvě aktivity, které je reprezentována jako šipka z Návrháře zdrojové do cílové návrháře.  
  
### <a name="flowchart-activity-properties"></a>Vývojový diagram vlastnosti aktivit  
 Následující tabulce je zobrazena <xref:System.Activities.Statements.Flowchart> vlastnosti a popisuje, jak se používají v návrháři. Tyto vlastnosti se dá upravit v mřížce vlastnost nebo na plochu návrháře.  
  
|Název vlastnosti|Požadováno|Použití|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|Určuje zobrazovaný název Návrhář aktivity v hlavičce. Výchozí hodnota je Vývojový diagram. Hodnotu lze upravit v **vlastnosti** okno nebo přímo v hlavičce Návrhář aktivity.<br /><br /> I když <xref:System.Activities.Activity.DisplayName%2A> striktně nevyžaduje, je osvědčeným postupem použít.|  
|<xref:System.Activities.Statements.Flowchart.Variables%2A>|False|Kolekce proměnných, které jsou určené v rámci to <xref:System.Activities.Statements.Flowchart> sdílet stavu ve jeho podřízené aktivity.|  
|<xref:System.Activities.Statements.Flowchart.StartNode%2A>|False|<xref:System.Activities.Statements.FlowNode> Tedy spuštěna při <xref:System.Activities.Statements.Flowchart> spustí.|  
|<xref:System.Activities.Statements.Flowchart.Nodes%2A>|False|Obsahuje kolekci <xref:System.Activities.Statements.FlowNode> objekty v <xref:System.Activities.Statements.Flowchart>.|  
  
## <a name="see-also"></a>Viz také  
 [Vývojový diagram](../workflow-designer/flowchart-activity-designers.md)   
 [FlowDecision](../workflow-designer/flowdecision-activity-designer.md)   
 [FlowSwitch\<T >](../workflow-designer/flowswitch-t-activity-designer.md)