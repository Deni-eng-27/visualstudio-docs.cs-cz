---
title: Návrhář aktivity Návrhář postupu provádění – přiřazení
description: Přečtěte si, jak můžete pomocí návrháře aktivity přiřazení vytvořit a nakonfigurovat aktivitu přiřazení a jak aktivita přiřazení přiřadí hodnotu proměnné nebo argumentu.
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Statements.Assign.UI
ms.assetid: ba3feb3c-f144-47ea-926d-cf752b804153
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 9d8601951cfaba3f246e8488ab23c9b6ccad0d01
ms.sourcegitcommit: ed26b6e313b766c4d92764c303954e2385c6693e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/10/2020
ms.locfileid: "94438188"
---
# <a name="assign-activity-designer"></a>Návrhář aktivity Assign

Návrhář **přiřazení** aktivity se používá k vytvoření a konfiguraci <xref:System.Activities.Statements.Assign> aktivity.

## <a name="the-assign-activity"></a>Aktivita přiřazení

<xref:System.Activities.Statements.Assign>Aktivita přiřadí hodnotu proměnné nebo argumentu.

### <a name="using-the-assign-activity-designer"></a>Použití návrháře přiřazení aktivity

Návrháře **přiřazení** aktivity lze najít v kategorii **primitivních** prvků sady **nástrojů** , ke které se dostanete kliknutím na kartu **panel** nástrojů (případně můžete vybrat možnost **Sada nástrojů** v nabídce **zobrazení** nebo CTRL + ALT + X).)

Návrháře **přiřazení** aktivity lze přetáhnout ze **sady nástrojů** a přetáhnout na Návrhář postupu provádění plochu, kde jsou umístěny aktivity, například dovnitř <xref:System.Activities.Statements.Sequence> . Vyřazením návrháře aktivity **přiřazení** <xref:System.Activities.Statements.Assign> se vytvoří aktivita s výchozím **názvem DisplayName** (přiřadit). Je <xref:System.Activities.Activity.DisplayName%2A> možné upravit v záhlaví návrháře aktivity **přiřazení** nebo v poli **DisplayName** v mřížce vlastností.

### <a name="the-assign-properties"></a>Vlastnosti přiřazení

V následující tabulce jsou uvedeny <xref:System.Activities.Statements.Assign> vlastnosti a popisuje, jak se používají v návrháři. Tyto vlastnosti se dají upravovat v mřížce vlastností a některé z nich je možné upravovat na Návrhář postupu provádění povrchu.

|Název vlastnosti|Požaduje se|Využití|
|-|--------------|-|
|<xref:System.Activities.Activity.DisplayName%2A>|Nepravda|Popisný název <xref:System.Activities.Statements.Assign> aktivity Výchozí hodnota je přiřazení. I když není <xref:System.Activities.Activity.DisplayName%2A> hodnota striktně nutná, je osvědčeným postupem použití jednoho.|
|<xref:System.Activities.Statements.Assign.To%2A>|Pravda|Proměnná nebo argument, ke kterému <xref:System.Activities.Statements.Assign.Value%2A> je přiřazena. Hodnota musí být platným identifikátorem Visual Basic. Chcete-li nastavit vlastnost, zadejte výraz Visual Basic do pole **do** v Návrháři **přiřazení** aktivity nebo v mřížce vlastností.|
|<xref:System.Activities.Statements.Assign.Value%2A>|Pravda|Hodnota, která je přiřazena proměnné. Chcete-li nastavit <xref:System.Activities.Statements.Assign.Value%2A> , zadejte výraz Visual Basic do pole **hodnota** v Návrháři **přiřazení** aktivity nebo v mřížce vlastností.|

## <a name="see-also"></a>Viz také

- [Primitiva](../workflow-designer/primitives-activity-designers.md)
- [Zpoždění](../workflow-designer/delay-activity-designer.md)
- [InvokeMethod](../workflow-designer/invokemethod-activity-designer.md)
- [WriteLine](../workflow-designer/writeline-activity-designer.md)