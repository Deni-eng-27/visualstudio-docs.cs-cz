---
title: Dialogové okno Návrhář postupu provádění – přidat Inicializátoři CorrelationInitializers
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- AddCorrelationInitializers.UI
ms.assetid: c0517467-d54a-4ee6-aef0-c19b96b6f395
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 5d69b53e21d11cba99a9e897871c6f9e0320352f
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/19/2019
ms.locfileid: "72650776"
---
# <a name="add-correlationinitializers-dialog-box"></a>Dialogové okno Přidat inicializátory korelace

Dialogové okno **Přidat Inicializátory korelace** se používá v Návrhář postupu provádění ke konfiguraci vlastností **inicializátoři CorrelationInitializers** aktivit <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.SendReply> a <xref:System.ServiceModel.Activities.ReceiveReply>. Další informace o návrhářech aktivity, které používají toto pole, najdete v tématech [posílání](../workflow-designer/send-activity-designer.md), [Receive](../workflow-designer/receive-activity-designer.md), [ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md)a [SendAndReceiveReply](../workflow-designer/sendandreceivereply-template-designer.md) .

Inicializátory korelace v kolekci určené pomocí tohoto dialogového okna můžou inicializovat následující korelace mezi aktivitami zasílání zpráv:

- založené na dotazech
- kontext
- kontext zpětného volání
- požadavek a odpověď

Následující tabulka popisuje prvky uživatelského rozhraní (UI) v dialogovém okně **Přidat Inicializátory korelace** :

|Prvek uživatelského rozhraní (UI)|Popis|
|-|-----------------|
|**Přidat inicializátor**|Kliknutím na pole **přidat inicializaci** přidejte do kolekce další inicializátor.|
|**Typ korelace**|Určuje typ inicializátoru korelace. Existují čtyři typy, ze kterých si můžete vybrat:<br /><br /> 1. inicializátor korelace zpětného volání pro určení <xref:System.ServiceModel.Activities.CallbackCorrelationInitializer>.<br />2. inicializátor korelace kontextu pro určení <xref:System.ServiceModel.Activities.CorrelationInitializer>.<br />3. inicializátor korelace požadavek-odpověď pro určení <xref:System.ServiceModel.Activities.RequestReplyCorrelationInitializer>.<br />4. inicializátor korelace dotazu pro určení <xref:System.ServiceModel.Activities.QueryCorrelationInitializer>.<br /><br /> Postup úpravy **CorrelationType**<br /><br /> 1. karta do konkrétního řádku v ovládacím prvku **Přidat inicializátor inicializátoru**<br />2. Pokud chcete nastavit fokus na **CorrelationTypeComboBox**, stiskněte klávesu **CTRL** +**TAB**.<br />3. Kliknutím na tlačítko Alt + šipka dolů zobrazíte okno se **seznamem** a upravíte ho.|
|**Dotazy XPath**|Pár klíč/hodnota, který obsahuje dotazy použité k extrakci dat korelace z příchozích a odchozích zpráv. Tento seznam je platný pouze při použití typů <xref:System.ServiceModel.Activities.QueryCorrelationInitializer>.|

## <a name="to-launch-the-add-correlation-initializers-dialog-box"></a>Spuštění dialogového okna Přidat Inicializátory korelace

 Dialogové okno **Přidat Inicializátory korelace** se používá v návrhářích **Odeslat**, **přijmout**, **ReceiveAndSendReply**a **SendAndReceiveReply** . Přístup k nim je podobný v každém případě a k ilustraci tohoto postupu slouží i případ, který zahrnuje návrháře **Receive** .

 Návrhář aktivity **Receive** lze přetáhnout ze **sady nástrojů** a vyřadit na Návrhář postupu provádění plochu všude, kde jsou umístěny aktivity. Vyřazením návrháře aktivity **Receive** se vytvoří aktivita <xref:System.ServiceModel.Activities.Receive> s výchozím <xref:System.Activities.Activity.DisplayName%2A> příjmu. Vyberte Návrhář aktivity **Receive** a klikněte na tlačítko se třemi tečkami vedle textu (kolekce) pro vlastnost **inicializátoři CorrelationInitializers** v mřížce vlastností pro zobrazení dialogového okna **Přidat Inicializátory korelace** .

## <a name="see-also"></a>Viz také:

- [Dialogové okno Inicializace korelace](../workflow-designer/initialize-correlation-dialog-box.md)