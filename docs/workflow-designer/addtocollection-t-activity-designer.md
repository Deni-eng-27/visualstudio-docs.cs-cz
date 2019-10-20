---
title: Návrhář aktivity <T> Návrhář postupu provádění AddToCollection
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Statements.AddToCollection`1.UI
ms.assetid: f7fc0702-164e-4370-8946-bb2f9f9384b7
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e8aa11f93b702f48d93710b9993769289ebc8ffa
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/19/2019
ms.locfileid: "72650749"
---
# <a name="addtocollectiont-activity-designer"></a>Návrhář aktivity > AddToCollection \<T

Návrhář aktivity **\<T > AddToCollection** slouží k vytvoření a konfiguraci aktivity <xref:System.Activities.Statements.AddToCollection%601>.

## <a name="the-addtocollectiont-activity"></a>Aktivita > AddToCollection \<T

Aktivita <xref:System.Activities.Statements.AddToCollection%601> přidá položku do kolekce.

### <a name="using-the-addtocollectiont-activity-designer"></a>Použití návrháře aktivit > AddToCollection \<T

Návrhář aktivity **AddToCollection \<T >** lze najít v kategorii **kolekce** sady **nástrojů**, ke které se dostanete kliknutím na kartu **panelu nástrojů** Návrhář postupu provádění. Případně vyberte v nabídce **zobrazení** možnost **Sada nástrojů** nebo stiskněte klávesovou **zkratku CTRL** +**ALT** +**X**.

Návrhář aktivity **AddToCollection \<T >** lze přetáhnout ze **sady nástrojů** a vyřadit na Návrhář postupu provádění plochu všude, kde jsou umístěny aktivity, například uvnitř <xref:System.Activities.Statements.Sequence>. Vyřazení **AddToCollection \<T >** návrháři aktivit vytvoří <xref:System.Activities.Statements.AddToCollection%601> aktivitu s výchozím <xref:System.Activities.Activity.DisplayName%2A> AddToCollection < Int32 \>. (Ve výchozím nastavení je *pro TypeArgument* typu **Int32**. Pro TypeArgument lze změnit v mřížce vlastností.) Hodnotu <xref:System.Activities.Activity.DisplayName%2A> lze upravit v hlavičce návrháře aktivity aplikace **AddToCollection < t \>** nebo v poli **DisplayName** v mřížce vlastností. Ostatní vlastnosti je nutné upravit v mřížce vlastností.

### <a name="the-addtocollectiont-properties"></a>Vlastnosti AddToCollection \<T >

V následující tabulce jsou uvedeny vlastnosti <xref:System.Activities.Statements.AddToCollection%601> a popisuje, jak se používají v návrháři.

|Název vlastnosti|Požadováno|Použití|
|-|--------------|-|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Popisný název aktivity <xref:System.Activities.Statements.AddToCollection%601>. Výchozí hodnota je AddToCollection < Int32 \>. I když hodnota <xref:System.Activities.Activity.DisplayName%2A> není bezpodmínečně nutná, je osvědčeným postupem použití jednoho.|
|<xref:System.Activities.Statements.AddToCollection%601.Item%2A>|Podmínka|Položka, kterou chcete přidat do kolekce \<T >. Tato položka je typu *T*, který je typu *pro TypeArgument*. Chcete-li zadat položku, zadejte výraz Visual Basic v mřížce vlastností.|
|<xref:System.Activities.Statements.AddToCollection%601.Collection%2A>|Podmínka|Kolekce, do které má být položka přidána. Tato kolekce je typu **ICollection < pro typeargument \>** . Chcete-li zadat kolekci, zadejte výraz Visual Basic v mřížce vlastností.|
|*Pro TypeArgument*|Podmínka|Typ T položek obsažených v <xref:System.Collections.Generic.ICollection%601>. Ve výchozím nastavení je tento typ *pro TypeArgument* nastaven na hodnotu **Int32**. Chcete-li změnit typ, změňte hodnotu *pro TypeArgument* v poli se seznamem v mřížce vlastností.|

## <a name="see-also"></a>Viz také:

- [Kolekce](../workflow-designer/collection-activity-designers.md)
- [Návrhář aktivity > AddToCollection \<T](../workflow-designer/addtocollection-t-activity-designer.md)
- [ClearCollection\<T>](../workflow-designer/clearcollection-t-activity-designer.md)
- [ExistsInCollection\<T>](../workflow-designer/existsincollection-t-activity-designer.md)
- [RemoveFromCollection\<T>](../workflow-designer/removefromcollection-t-activity-designer.md)