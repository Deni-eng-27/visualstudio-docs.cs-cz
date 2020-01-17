---
title: Návrhář aktivity Návrhář postupu provádění – if
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Statements.If.UI
ms.assetid: 930a8fa2-db98-43e9-ad6d-a85cc7a6519a
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 099be38c5585fe19c00b31c00ac3a7ddcd3d7fe2
ms.sourcegitcommit: f3f668ecaf11b4c2738ebc91923c6b5e38e74670
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/16/2020
ms.locfileid: "76111445"
---
# <a name="if-activity-designer"></a>Návrhář aktivity If

Aktivita <xref:System.Activities.Statements.If> vyhodnocuje podmínku a spustí aktivitu v závislosti na výsledcích tohoto vyhodnocení. Tato aktivita je nejužitečnější při použití stylu procedurálního modelování programování. Aktivita <xref:System.Activities.Statements.If> může být vnořená v rámci aktivity <xref:System.Activities.Statements.Sequence> nebo aktivity <xref:System.Activities.Statements.Parallel>, například. Pokud používáte aktivitu <xref:System.Activities.Statements.Flowchart>, zvažte místo toho použití <xref:System.Activities.Statements.FlowDecision> aktivity.

## <a name="if-properties-in-the-workflow-designer"></a>Pokud se v Návrhář postupu provádění vlastnosti

Následující tabulka uvádí nejužitečnější vlastnosti <xref:System.Activities.Statements.If> aktivity a popisuje jejich použití v návrháři.

|Název vlastnosti|Požadováno|Použití|
|-|--------------|-|
|<xref:System.Activities.Statements.If.Condition%2A>|Pravda|Podmínka, která určuje, která podřízená aktivita má být provedena. Chcete-li nastavit <xref:System.Activities.Statements.If.Condition%2A>, zadejte výraz Visual Basic do pole **Podmínka** v Návrháři aktivity **if** nebo v mřížce vlastností.|
|<xref:System.Activities.Statements.If.Else%2A>|Nepravda|Aktivita, která se má provést, pokud je <xref:System.Activities.Statements.If.Condition%2A> **false** Chcete **-li přidat** aktivitu, která je spouštěna <xref:System.Activities.Statements.If.Else%2A> větví, přetáhněte aktivitu ze **sady nástrojů** do pole **Else** v Návrháři aktivity s textem nápovědy "Sem přetáhněte aktivitu".|
|<xref:System.Activities.Statements.If.Then%2A>|Nepravda|Aktivita, která se má provést, pokud je <xref:System.Activities.Statements.If.Condition%2A> **true**. Chcete-li přidat aktivitu, která je spouštěna <xref:System.Activities.Statements.If.Then%2A> větví, přetáhněte aktivitu ze **sady nástrojů** do pole **a** v Návrháři aktivity **if** s textem nápovědy "Sem přetáhněte aktivitu".|

## <a name="see-also"></a>Viz také:

- [Sequence](../workflow-designer/sequence-activity-designer.md)
- [Parallel](../workflow-designer/parallel-activity-designer.md)
- [Tok řízení](../workflow-designer/control-flow-activity-designers.md)
