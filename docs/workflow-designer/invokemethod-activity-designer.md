---
title: Návrhář postupu provádění - InvokeMethod Návrhář aktivity
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Activities.Statements.InvokeMethod.UI
ms.assetid: 15e6efdc-52ca-46d8-9c5e-063f7c8265a6
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b612966da1244c745edbe8a5c92b1b300554a388
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="invokemethod-activity-designer"></a>Návrhář aktivity InvokeMethod

**InvokeMethod** designer se používá k vytvoření a konfigurace <xref:System.Activities.Statements.InvokeMethod> aktivity.

## <a name="the-invokemethod-activity"></a>InvokeMethod aktivity

<xref:System.Activities.Statements.InvokeMethod> Volá veřejná metoda zadaný objekt nebo typu.

### <a name="using-the-invokemethod-activity-designer"></a>Pomocí návrháře InvokeMethod aktivity
 **InvokeMethod** Návrhář aktivity naleznete v **primitiv** kategorii **sada nástrojů**, který přistupuje kliknutím **sady nástrojů** kartě v Návrháři pracovních postupů (případně vyberte možnost **nástrojů** z **zobrazení** nabídky nebo CRTL + ALT + X.)

 **InvokeMethod** Návrhář aktivity můžete přetáhnout z **sada nástrojů** a vyřadit na povrch návrháře pracovních postupů, kde ever aktivity jsou obvykle umístěny, například jako uvnitř <xref:System.Activities.Statements.Sequence>. Tím se vytvoří <xref:System.Activities.Statements.InvokeMethod> aktivitu výchozí <xref:System.Activities.Activity.DisplayName%2A> z InvokeMethod. <xref:System.Activities.Activity.DisplayName%2A> Lze upravit v hlavičce **InvokeMethod** Návrhář aktivity nebo v **DisplayName** pole mřížku vlastností.

### <a name="the-invokemethod-properties"></a>Vlastnosti InvokeMethod
 Následující tabulce je zobrazena <xref:System.Activities.Statements.InvokeMethod> vlastnosti a popisuje, jak se používají v návrháři. Tyto vlastnosti lze upravit v tabulce vlastností a některé můžete upravit na povrchu Designerdesigner pracovního postupu.

|Název vlastnosti|Požadováno|Použití|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Popisný název <xref:System.Activities.Statements.InvokeMethod> aktivity. Výchozí hodnota je InvokeMethod.<br /><br /> I když <xref:System.Activities.Activity.DisplayName%2A> striktně nevyžaduje, je osvědčeným postupem použít.|
|<xref:System.Activities.Statements.InvokeMethod.MethodName%2A>|Hodnota TRUE|Název metody, která se má volat, když aktivita provede. Vyvolání metody musí být deklarována jako **veřejné**. Tuto vlastnost lze upravit na plochu návrháře. Toto je povinná vlastnost.|
|<xref:System.Activities.Statements.InvokeMethod.Parameters%2A>|False|Kolekce parametrů vyvolání metody. Parametry musí být přidány do kolekce ve stejném pořadí, ve kterém se zobrazují v podpis metody. V tabulce vlastností klikněte na tlačítko se třemi tečkami v **parametry** pole, zobrazuje **parametry** dialogové okno, abyste mohli tuto vlastnost nastavit. Klikněte **vytvořit Argument** tlačítko přidáte parametry.|
|<xref:System.Activities.Statements.InvokeMethod.Result%2A>|False|Návratová hodnota volání metody.|
|<xref:System.Activities.Statements.InvokeMethod.RunAsynchronously%2A>|Hodnota TRUE|Určuje, zda je volána metoda asynchronně. Výchozí hodnota je **False**.|
|<xref:System.Activities.Statements.InvokeMethod.TargetObject%2A>|False|Objekt, který obsahuje metodu volat. Tuto vlastnost lze upravit na plochu návrháře.<br /><br /> Buď <xref:System.Activities.Statements.InvokeMethod.TargetObject%2A> nebo <xref:System.Activities.Statements.InvokeMethod.TargetType%2A> je potřeba nastavit.|
|<xref:System.Activities.Statements.InvokeMethod.TargetType%2A>|False|Typ <xref:System.Activities.Statements.InvokeMethod.TargetObject%2A>. Tuto vlastnost lze upravit na plochu návrháře. Tuto vlastnost musíte nastavit pouze v případě, že je metoda volána statická.|

 Předávání parametrů jako C# **out** parametr (například `Method1(out myParam)),` byste měli používat **OutArgument** místo **InOutArgument**

 Metody s názvem argumenty **TargetObject** nebo **výsledek** nelze volat pomocí <xref:System.Activities.Statements.InvokeMethod> aktivity. Důvodem je, že <xref:System.Activities.Statements.InvokeMethod> aktivity registrů <xref:System.Activities.Statements.InvokeMethod.GenericTypeArguments%2A>, <xref:System.Activities.Statements.InvokeMethod.TargetObject%2A> a <xref:System.Activities.Statements.InvokeMethod.Result%2A> v <xref:System.Activities.Activity.CacheMetadata%2A>.

 Algoritmus pro registraci parametrů v <xref:System.Activities.Activity.CacheMetadata%2A> je znázorněno v následujícím seznamu:

1.  Zaregistrovat <xref:System.Activities.Statements.InvokeMethod.TargetObject%2A> argument.

2.  Zaregistrovat <xref:System.Activities.Statements.InvokeMethod.Result%2A> argument.

3.  Iterace <xref:System.Activities.Statements.InvokeMethod.Parameters%2A> kolekce a zaregistrovat každý argument.

 Výsledný výjimka je typu <xref:System.Activities.InvalidWorkflowException> s následující zprávou: 'InvokeMethod': do proměnné, RuntimeArgument nebo DelegateArgument už existuje s názvem 'TargetObject'. Názvy musí být jedinečné v rámci rozsahu prostředí.

 Toto omezení se nevztahuje na <xref:System.Activities.Statements.InvokeMethod.TargetType%2A> a <xref:System.Activities.Statements.InvokeMethod.RunAsynchronously%2A> vzhledem k tomu, že nejsou argumenty pracovního postupu a proto nejsou registrované v <xref:System.Activities.Statements.InvokeMethod.GenericTypeArguments%2A> kolekce <xref:System.Activities.Statements.InvokeMethod> aktivity v <xref:System.Activities.Activity.CacheMetadata%2A> metoda.

## <a name="see-also"></a>Viz také

- [Primitiva](../workflow-designer/primitives-activity-designers.md)
- [přiřazení](../workflow-designer/assign-activity-designer.md)
- [Zpoždění](../workflow-designer/delay-activity-designer.md)
- [WriteLine](../workflow-designer/writeline-activity-designer.md)