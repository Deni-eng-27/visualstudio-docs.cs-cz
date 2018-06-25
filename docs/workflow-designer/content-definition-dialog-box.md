---
title: Návrhář postupu provádění – dialogové okno Definice obsahu
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- MessageContent.UI
ms.assetid: 7e4237c3-90a1-4149-bd8a-3643d1dde0df
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: cc434e35755b04054d1e24da97e8a4699af7df0e
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/25/2018
ms.locfileid: "36757948"
---
# <a name="content-definition-dialog-box"></a>Dialogové okno Definice obsahu

**Obsahu definice** dialogové okno v Návrháři pracovních postupů slouží ke konfiguraci **obsahu** vlastnosti <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.SendReply>, a <xref:System.ServiceModel.Activities.ReceiveReply> aktivity. Další informace o návrháře aktivit, které používají toto políčko, najdete v článku [odeslat](../workflow-designer/send-activity-designer.md), [Receive](../workflow-designer/receive-activity-designer.md), [ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md), a [SendAndReceiveReply ](../workflow-designer/sendandreceivereply-template-designer.md) témata.

Následující tabulka popisuje prvky uživatelského rozhraní (UI) **inicializovat korelace** dialogové okno:

|Prvek uživatelského rozhraní (UI)|Popis|
|----------------|-----------------|
|**Zpráva**|Určuje zprávu, která obsah s **zprávy data** výraz textového pole a zadejte pomocí **typ zprávy** rozevíracího seznamu. Ve výchozím nastavení **obsahu definice** používá <xref:System.ServiceModel.Activities.ReceiveMessageContent>, která očekává <xref:System.ServiceModel.Channels.Message> nebo zprávu smlouvy type v rámci služby definice pracovního postupu.|
|**Parametry**|Klikněte **parametry** přepínač použít <xref:System.ServiceModel.Activities.ReceiveParametersContent>, která očekává kontraktu dat. Použít mřížku dat nastavit obecné kolekce <xref:System.Activities.OutArgument> jejichž hodnoty jsou přiřazeny k proměnné parametry v aktuálním pracovním postupu dvojice klíč/hodnota.|

**Obsahu definice** dialogové okno používá **odeslat**, **Receive**, **ReceiveAndSendReply**, a  **SendAndReceiveReply** Designer. K nim přistupovat je podobný v každém případě a Receive případě zde slouží k znázorňují postup.

**Receive** Návrhář aktivity můžete přetáhnout z **sada nástrojů** a vyřadit na povrch návrháře pracovních postupů bez ohledu na aktivity jsou obvykle umístěny. Tím se vytvoří <xref:System.ServiceModel.Activities.Receive> aktivitu výchozí <xref:System.Activities.Activity.DisplayName%2A> Receive. Vyberte **Receive** Návrhář aktivity a klikněte na tlačítko se třemi tečkami vedle textu u (obsah) **obsahu** vlastnost mřížku vlastností pro **obsahu definice**dialogové okno se objeví.

Obsah lze zadat v rámci **zpráva** část <xref:System.ServiceModel.Activities.ReceiveMessageContent> aktivity nebo uvnitř **parametr** část <xref:System.ServiceModel.Activities.ReceiveParametersContent> aktivity.

## <a name="see-also"></a>Viz také:

- [Nápověda k uživatelskému rozhraní návrháře postupu provádění](../workflow-designer/workflow-designer-ui-help.md)