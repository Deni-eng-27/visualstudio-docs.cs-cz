---
title: Návrhář aktivity Návrhář postupu provádění-WriteLine
description: Přečtěte si o aktivitě WriteLine a o tom, jak můžete pomocí návrháře aktivity WriteLine vytvořit a nakonfigurovat aktivitu WriteLine.
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Statements.WriteLine.UI
ms.assetid: 1b5f29a8-b7fd-477e-949e-2f689cae3c96
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 03aedaf522924266b0951ec189e96fb3f83c142c
ms.sourcegitcommit: ed26b6e313b766c4d92764c303954e2385c6693e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/10/2020
ms.locfileid: "94433658"
---
# <a name="writeline-activity-designer"></a>Návrhář aktivity WriteLine

Návrhář aktivity **WriteLine** slouží k vytvoření a konfiguraci <xref:System.Activities.Statements.WriteLine> aktivity.

## <a name="the-writeline-activity"></a>Aktivita WriteLine

<xref:System.Activities.Statements.WriteLine>Aktivita zapisuje text do zadaného <xref:System.IO.TextWriter> objektu. Pokud <xref:System.IO.TextWriter> není zadaný, <xref:System.Activities.Statements.WriteLine> zapíše text do konzoly.

### <a name="using-the-writeline-activity-designer"></a>Použití návrháře aktivity WriteLine

Přístup k Návrháři aktivity **WriteLine** v kategorii **primitivních** prvků sady **nástrojů** Návrhář aktivity **WriteLine** lze přetáhnout ze **sady nástrojů** a vyřadit na Návrhář postupu provádění plochu všude, kde jsou obvykle umístěny aktivity, například dovnitř <xref:System.Activities.Statements.Sequence> . Tím se vytvoří <xref:System.Activities.Statements.WriteLine> aktivita s výchozím nastavením <xref:System.Activities.Activity.DisplayName%2A> WriteLine. <xref:System.Activities.Activity.DisplayName%2A>Lze upravit v záhlaví návrháře aktivity **WriteLine** nebo v poli **DisplayName** v mřížce vlastností.

### <a name="the-writeline-properties"></a>Vlastnosti WriteLine

V následující tabulce jsou uvedeny <xref:System.Activities.Statements.WriteLine> vlastnosti a popisuje, jak se používají v návrháři. Tyto vlastnosti se dají upravovat v mřížce vlastností a některé z nich je možné upravovat na Návrhář postupu provádění povrchu.

|Název vlastnosti|Požaduje se|Využití|
|-|--------------|-|
|<xref:System.Activities.Activity.DisplayName%2A>|Nepravda|Popisný název <xref:System.Activities.Statements.WriteLine> aktivity Výchozí hodnota je WriteLine. I když <xref:System.Activities.Activity.DisplayName%2A> není bezpodmínečně nutné, je vhodné použít jeden.|
|<xref:System.Activities.Statements.WriteLine.Text%2A>|Nepravda|Text, který se má zapsat Chcete-li nastavit vlastnost, zadejte výraz Visual Basic do **textového** pole v Návrháři aktivity **WriteLine** nebo v mřížce vlastností.|
|<xref:System.Activities.Statements.WriteLine.TextWriter%2A>|Nepravda|<xref:System.IO.TextWriter>Do které <xref:System.Activities.Statements.WriteLine> zapisuje <xref:System.Activities.Statements.WriteLine.Text%2A> . Výchozím nastavením je konzola.|

## <a name="see-also"></a>Viz také

- [Primitiva](../workflow-designer/primitives-activity-designers.md)
- [Řadit](../workflow-designer/assign-activity-designer.md)
- [Zpoždění](../workflow-designer/delay-activity-designer.md)
- [InvokeMethod](../workflow-designer/invokemethod-activity-designer.md)
