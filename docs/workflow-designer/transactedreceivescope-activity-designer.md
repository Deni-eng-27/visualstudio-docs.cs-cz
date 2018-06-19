---
title: Návrhář postupu provádění - TransactedReceiveScope Návrhář aktivity
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.ServiceModel.Activities.TransactedReceiveScope.UI
ms.assetid: 7ca93aad-4e83-4d81-90f4-998ee114d9b6
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c7f5c4cd48cc98d58da278ac53c1a829d15c43cd
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31976849"
---
# <a name="transactedreceivescope-activity-designer"></a>Návrhář aktivity TransactedReceiveScope

**TransactedReceiveScope** designer se používá k vytvoření a konfigurace <xref:System.ServiceModel.Activities.TransactedReceiveScope> aktivity.

## <a name="the-transactedreceivescope-activity"></a>TransactedReceiveScope aktivity

<xref:System.ServiceModel.Activities.TransactedReceiveScope> Aktivity umožňuje tok transakcí do serveru transakce vytvořené pracovního postupu nebo dispečera.

### <a name="using-the-transactedreceivescope-activity-designer"></a>Pomocí návrháře TransactedReceiveScope aktivity
 **TransactedReceiveScope** Návrhář aktivity naleznete v **zasílání zpráv** kategorii **sada nástrojů**, který přistupuje kliknutím **sada nástrojů**  kartě v Návrháři pracovních postupů (případně vyberte možnost **nástrojů** z **zobrazení** nabídky nebo CTRL + ALT + X.)

 **TransactedReceiveScope** Návrhář aktivity můžete přetáhnout z **sada nástrojů** a vyřadit na povrch návrháře pracovních postupů bez ohledu na aktivity jsou obvykle umístěny. Tím se vytvoří <xref:System.ServiceModel.Activities.TransactedReceiveScope> aktivitu výchozí **DisplayName** z TransactedReceiveScope. <xref:System.Activities.Activity.DisplayName%2A> Lze upravit v hlavičce **TransactedReceiveScope** Návrhář aktivity nebo v **DisplayName** pole mřížku vlastností.

 **TransactedReceiveScope** Návrhář obsahuje **požadavku** a **textu** polí. Ty se používají ke konfiguraci <xref:System.ServiceModel.Activities.TransactedReceiveScope.Request%2A> vlastnosti, která určuje <xref:System.ServiceModel.Activities.Receive> aktivity a <xref:System.ServiceModel.Activities.TransactedReceiveScope.Body%2A> vlastnosti, která určuje některé další <xref:System.Activities.Activity>. <xref:System.ServiceModel.Activities.TransactedReceiveScope.Request%2A> Vytvoří transakci. Transakce poté je provedena vedlejším rozsahu <xref:System.ServiceModel.Activities.TransactedReceiveScope.Body%2A> tak, aby všechny aktivity v rámci tohoto rozsahu provede v této transakci.

### <a name="the-transactedreceivescope-properties"></a>Vlastnosti TransactedReceiveScope
 Následující tabulce je zobrazena <xref:System.ServiceModel.Activities.TransactedReceiveScope> vlastnosti a popisuje, jak se používají v návrháři. Tyto <xref:System.Activities.Activity.DisplayName%2A> vlastnost lze upravit v mřížce vlastnost nebo na plochu návrháře pracovních postupů, ale ostatní musí upravit na návrhovou plochu.

|Název vlastnosti|Požadováno|Použití|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Volitelné popisný název <xref:System.ServiceModel.Activities.TransactedReceiveScope> aktivity. Výchozí hodnota je TransactedReceiveScope.<br /><br /> I když <xref:System.Activities.Activity.DisplayName%2A> název není nezbytně nutné, je osvědčeným postupem použít zobrazovaný název.|
|<xref:System.ServiceModel.Activities.TransactedReceiveScope.Request%2A>|Hodnota TRUE|Vyřazuje <xref:System.ServiceModel.Activities.Receive> aktivity do **požadavku** bloku na plochu návrháře aktivit.|
|<xref:System.ServiceModel.Activities.TransactedReceiveScope.Body%2A>|False|Vyřazuje <xref:System.Activities.Activity> do **textu** bloku na plochu návrháře aktivit.|

## <a name="see-also"></a>Viz také

- [CorrelationScope](../workflow-designer/correlationscope-activity-designer.md)
- [InitializeCorrelation](../workflow-designer/initializecorrelation-activity-designer.md)
- [Přijímat](../workflow-designer/receive-activity-designer.md)
- [ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md)
- [Odeslat](../workflow-designer/send-activity-designer.md)
- [SendAndReceiveReply](../workflow-designer/sendandreceivereply-template-designer.md)