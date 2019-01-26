---
title: Návrhář postupu provádění – DoWhile návrháře aktivit
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
f1_keywords:
- System.Activities.Statements.DoWhile.UI
ms.assetid: 948deb35-d72f-462b-bea6-4b119c10a148
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 6a674cf58740fe914d00ae1ebfdeb5b642716e37
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54960552"
---
# <a name="dowhile-activity-designer"></a>Návrhář aktivity DoWhile

<xref:System.Activities.Statements.DoWhile> Aktivita provádí aktivity obsažené v jeho <xref:System.Activities.Statements.DoWhile.Body%2A> alespoň jednou, dokud je zadaná podmínka vyhodnocena jako **false**. Pokud potřebujete aktivity obsažené v těle smyčky mají být provedeny nulakrát nebo vícekrát, použijte <xref:System.Activities.Statements.While> aktivity místo.

## <a name="dowhile-properties-in-the-workflow-designer"></a>Vlastnosti DoWhile v Návrháři postupu provádění

V následující tabulce jsou uvedeny nejužitečnější <xref:System.Activities.Statements.DoWhile> vlastnosti aktivity a popisuje, jak je používat v Návrháři:

|Název vlastnosti|Požadováno|Použití|
|-|--------------|-|
|<xref:System.Activities.Statements.DoWhile.Body%2A>|False|Aktivity ke spuštění, dokud podmínka **true**. Chcete-li přidat <xref:System.Activities.Statements.DoWhile.Body%2A> aktivity, rozevírací aktivitu z panelu nástrojů do **tělo** pole na **DoWhile** Návrhář aktivity s text nápovědy "Aktivity Sem přetáhněte".|
|<xref:System.Activities.Statements.DoWhile.Condition%2A>|Pravda|Podmínka k vyhodnocení po každé iteraci smyčky. Chcete-li nastavit <xref:System.Activities.Statements.DoWhile.Condition%2A>, zadejte výraz jazyka Visual Basic v **podmínku** pole na **DoWhile** aktivity návrháře nebo v mřížce vlastností.|

## <a name="see-also"></a>Viz také:

- [While](../workflow-designer/while-activity-designer.md)
- [Tok řízení](../workflow-designer/control-flow-activity-designers.md)