---
title: Návrhář postupu provádění - InvokeDelegate
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- InvokeDelegate Designer
- System.Activities.Statements.InvokeDelegate.UI
ms.assetid: 289a7498-5127-453f-beb5-05f05b80d26f
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 511d73ea2992887f31bc8750cc9ba32934bddd91
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55925368"
---
# <a name="invokedelegate"></a>InvokeDelegate

**InvokeDelegate** Návrhář slouží k vytvoření a konfigurace <xref:System.Activities.Statements.InvokeDelegate> aktivity.

## <a name="the-invokedelegate-activity"></a>Aktivita InvokeDelegate

<xref:System.Activities.Statements.InvokeDelegate> Volá veřejný delegát.

### <a name="use-the-invokedelegate-activity-designer"></a>Použití návrháře aktivit InvokeDelegate

Přístup **InvokeDelegate** návrháře aktivit v **primitiv** kategorii **nástrojů**. **InvokeDelegate** návrháře aktivit můžete přetáhnout z **nástrojů** a vyřadit na povrch návrháře postupu provádění, pokud už aktivity jsou obvykle umístěny, například jako uvnitř <xref:System.Activities.Statements.Sequence>. Vyřazení Návrhář aktivity vytvoří <xref:System.Activities.Statements.InvokeDelegate> aktivity s výchozím <xref:System.Activities.Activity.DisplayName%2A> z InvokeDelegate. <xref:System.Activities.Activity.DisplayName%2A> Můžete upravovat v záhlaví **InvokeDelegate** Návrhář aktivity nebo v **DisplayName** pole mřížku vlastností.

### <a name="the-invokedelegate-properties"></a>Vlastnosti InvokeDelegate

Následující tabulka ukazuje <xref:System.Activities.Statements.InvokeDelegate> vlastnosti a popisuje, jak se používají v návrháři. Tyto vlastnosti můžete upravit v mřížce vlastností a můžete upravit některé na plochu návrháře postupu provádění.

|Název vlastnosti|Požadováno|Použití|
|-|--------------|-|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Popisný název <xref:System.Activities.Statements.InvokeDelegate> aktivity. Výchozí hodnota je InvokeDelegate.<br /><br /> I když <xref:System.Activities.Activity.DisplayName%2A> není bezpodmínečně nutné, doporučujeme použít jednu.|
|<xref:System.Activities.Statements.InvokeDelegate.Delegate%2A>|Pravda|Název <xref:System.Activities.ActivityDelegate> se volá, když tato aktivity spustí. Tuto vlastnost lze na návrhové ploše upravovat a je povinný.|
|<xref:System.Activities.Statements.InvokeDelegate.DelegateArguments%2A>|False|Argument kolekce volaný delegát. Klíče jsou názvy objektů parametr na <xref:System.Activities.ActivityDelegate>, a hodnoty jsou argumenty, jejíž výrazy jsou vyhodnoceny a přiřadili odpovídající parametr objekty. Chcete-li zobrazit **DelegateArguments** dialogové okno, kde můžete nastavit tuto vlastnost, klikněte na tlačítko se třemi tečkami v **DelegateArguments** pole mřížku vlastností. Klikněte na tlačítko **vytvořit Argument** pole, které chcete přidat argumenty.|

## <a name="see-also"></a>Viz také:

- [Postupy: Definice a používání delegátů aktivit v Návrháři postupu provádění](../workflow-designer/how-to-define-and-consume-activity-delegates-in-the-workflow-designer.md)