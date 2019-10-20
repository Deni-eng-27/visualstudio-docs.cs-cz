---
title: Návrhář postupu provádění – Návrhář aktivity throw
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Statements.Throw.UI
ms.assetid: 5e97c947-be39-4a1f-af04-000e2e09528a
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: fe6a530888c7c28c5c1556114db03a6cd7369fe6
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/19/2019
ms.locfileid: "72649852"
---
# <a name="throw-activity-designer"></a>Návrhář aktivity Throw

Návrhář aktivity **throw** slouží k vytvoření a konfiguraci aktivity <xref:System.Activities.Statements.Throw>.

## <a name="the-throw-activity"></a>Aktivita throw

Aktivita <xref:System.Activities.Statements.Throw> vyvolá výjimku.

### <a name="using-the-throw-activity-designer"></a>Použití návrháře aktivity throw

Přístup k Návrháři aktivity **throw** v kategorii **zpracování chyb** sady **nástrojů**.

Návrhář aktivity **throw** lze přetáhnout ze **sady nástrojů** a vyřadit na Návrhář postupu provádění plochu všude, kde jsou obvykle umístěny aktivity, například uvnitř <xref:System.Activities.Statements.Sequence>. Tím se vytvoří aktivita <xref:System.Activities.Statements.Throw> s výchozím **zobrazovaným názvem** pro vyvolání. Hodnotu <xref:System.Activities.Activity.DisplayName%2A> lze upravit v záhlaví návrháře aktivit **throw** nebo v poli **DisplayName** v mřížce vlastností. Vlastnost <xref:System.Activities.Statements.Throw.Exception%2A> musí být upravena v mřížce vlastností.

### <a name="the-throw-properties"></a>Vlastnosti throw

V následující tabulce jsou uvedeny vlastnosti <xref:System.Activities.Statements.Throw> a popisuje, jak se používají v návrháři.

|Název vlastnosti|Požadováno|Použití|
|-|--------------|-|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Určuje nepovinný popisný název aktivity <xref:System.Activities.Statements.Throw>. Výchozí hodnota je throw.|
|<xref:System.Activities.Statements.Throw.Exception%2A>|Podmínka|Výjimka, která se má vyvolat Tato výjimka musí být odvozena od <xref:System.Exception>. Chcete-li zadat výjimku, zadejte výraz Visual Basic v mřížce vlastností.|

## <a name="see-also"></a>Viz také:

- [Kolekce](../workflow-designer/collection-activity-designers.md)
- [Rethrow](../workflow-designer/rethrow-activity-designer.md)
- [Návrhář aktivity Throw](../workflow-designer/throw-activity-designer.md)
- [TryCatch](../workflow-designer/trycatch-activity-designer.md)