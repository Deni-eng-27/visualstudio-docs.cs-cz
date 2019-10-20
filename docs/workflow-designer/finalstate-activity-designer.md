---
title: Návrhář aktivity Návrhář postupu provádění – FinalState
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: aa186893-8775-40dd-981f-8593ead831d0
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
author: jillre
ms.openlocfilehash: b8f25167f3a67e2d1349354ce568c076697e3e73
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/19/2019
ms.locfileid: "72650463"
---
# <a name="finalstate-activity-designer"></a>Návrhář aktivity FinalState

Návrhář <xref:System.Activities.Core.Presentation.FinalState> slouží k vytvoření <xref:System.Activities.Statements.State>, který ukončuje instanci stavového počítače.

## <a name="using-the-finalstate-activity-designer"></a>Pomocí návrháře aktivity FinalState

Návrhář **FinalState** slouží k vytvoření <xref:System.Activities.Statements.State>, který je předem nakonfigurovaný jako ukončovací stav na stavovém stroji. @No__t_0, která je vytvořena pomocí návrháře aktivit <xref:System.Activities.Core.Presentation.FinalState> má vlastnost <xref:System.Activities.Statements.State.IsFinal%2A> nastavenou na **hodnotu true**, nemá žádnou <xref:System.Activities.Statements.State.Exit%2A> aktivitu a žádné přechody pocházející z nich. Pokud chcete pomocí návrháře aktivity <xref:System.Activities.Core.Presentation.FinalState> přidat aktivitu <xref:System.Activities.Statements.State>, která je předem nakonfigurovaná jako ukončovací stav ve stavovém počítači, přetáhněte návrháře aktivity **FinalState** z části **Stavový počítač** v **sadě nástrojů** a přetáhněte ho na Návrhář pracovního postupu. Návrhář aktivity <xref:System.Activities.Core.Presentation.FinalState> lze přetáhnout na <xref:System.Activities.Statements.StateMachine> a přechody přidané později. nebo je možné vytvořit přechod, protože je vyřazený Návrhář aktivity <xref:System.Activities.Core.Presentation.FinalState>. Další informace o vytváření přechodů najdete v tématu [přechod](../workflow-designer/transition-activity-designer.md).

### <a name="state-activity-properties-in-the-workflow-designer"></a>Vlastnosti aktivity stavu v Návrhář postupu provádění

V následující tabulce jsou uvedeny vlastnosti, které lze nastavit pomocí návrháře <xref:System.Activities.Core.Presentation.FinalState> a popisuje, jak se používají v návrháři. Některé z těchto vlastností lze upravit v mřížce vlastností a některé lze upravovat na návrhové ploše.

|Název vlastnosti|Požadováno|Použití|
|-|--------------|-|
|<xref:System.Activities.Statements.State.DisplayName%2A>|False|Určuje popisný název návrháře <xref:System.Activities.Statements.State> aktivity v hlavičce. Výchozí hodnota je **State (stav**). Hodnotu lze upravit v mřížce vlastností nebo přímo v záhlaví návrháře aktivit. @No__t_0 se používá v navigaci s popisem cesty, které se zobrazí v horní části návrháře pracovních postupů.<br /><br /> I když <xref:System.Activities.Statements.State.DisplayName%2A> není nezbytně nutné, je osvědčeným postupem použití jednoho.|
|<xref:System.Activities.Statements.State.Entry%2A>|False|Určuje akci, která nastane, když je tento stav převeden na. Tuto hodnotu lze nastavit přetáhnutím aktivity ze **sady nástrojů** a jejím přetažením do oddílu <xref:System.Activities.Statements.State.Entry%2A> ve stavu.|

## <a name="see-also"></a>Viz také:

- [StateMachine](../workflow-designer/statemachine-activity-designer.md)
- [Stav](../workflow-designer/state-activity-designer.md)
- [Transition](../workflow-designer/transition-activity-designer.md)