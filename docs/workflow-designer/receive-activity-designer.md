---
title: Návrhář aktivity Receive Návrhář postupu provádění
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.ServiceModel.Activities.Receive.UI
ms.assetid: f58d3c70-944d-4bb4-90a7-e68c103caddc
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8c9dc2a561ce424239df5ec08eb353453b831464
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/19/2019
ms.locfileid: "72650042"
---
# <a name="receive-activity-designer"></a>Návrhář aktivity Receive

Návrhář aktivity **Receive** slouží k vytvoření a konfiguraci aktivity <xref:System.ServiceModel.Activities.Receive>. Aktivita <xref:System.ServiceModel.Activities.Receive> je aktivita, která přijímá zprávu, která může být buď vestavěný typ, jako je například <xref:System.ServiceModel.Channels.Message>, <xref:System.IO.Stream> nebo <xref:System.Xml.Linq.XElement>, nebo kontrakt dat definovaný aplikací, kontrakt zprávy nebo třída XML, které lze serializovat.

## <a name="the-receive-activity"></a>Aktivita Receive

Aktivita <xref:System.ServiceModel.Activities.Receive> může obdržet jednu položku nebo více položek v závislosti na typu použitého obsahu pro příjem. Aktivita <xref:System.ServiceModel.Activities.SendReply> může být vázána na aktivitu <xref:System.ServiceModel.Activities.Receive>, která přijímá zprávu jako součást vzoru výměny zprávy žádosti nebo odpovědi na službu.

### <a name="using-the-receive-activity-designer"></a>Použití návrháře aktivity Receive

Přístup k Návrháři aktivity **Receive** v kategorii **zprávy** sady **nástrojů**. Návrhář aktivity **Receive** lze přetáhnout ze **sady nástrojů** a vyřadit na Návrhář postupu provádění plochu všude, kde jsou obvykle umístěny aktivity. Tím se vytvoří aktivita <xref:System.ServiceModel.Activities.Receive> s výchozím <xref:System.Activities.Activity.DisplayName%2A> příjmu. @No__t_0 lze upravit v hlavičce návrháře aktivity **Receive** nebo v poli **DisplayName** v mřížce vlastností.

Chcete-li vytvořit aktivitu <xref:System.ServiceModel.Activities.SendReply> a vytvořit její propojení s vybranou aktivitou <xref:System.ServiceModel.Activities.Receive>, klikněte pravým tlačítkem myši na Návrhář aktivity **Receive** , klikněte na položku **vytvořit aktivitu SendReply** v místní nabídce a **SendReplyToReceive** Designer se zobrazí pod  **Příjem** návrháře. Aktivita <xref:System.ServiceModel.Activities.SendReply> je aktivita, která odesílá odpověď jako součást vzoru výměny zprávy žádosti nebo odpovědi ve službě. Dá se nakonfigurovat pomocí návrháře **SendReplyToReceive** .

Alternativně lze pomocí návrháře šablon **ReceiveAndSendReply** v kategorii **zasílání zpráv** v **sadě nástrojů** vytvořit dvojici předem nakonfigurovaných <xref:System.ServiceModel.Activities.Receive> a <xref:System.ServiceModel.Activities.SendReply> aktivity. Další informace o použití šablony **ReceiveAndSendReply** a **SendReplyToReceive** naleznete v tématu [ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md) .

### <a name="the-receive-activity-properties"></a>Vlastnosti aktivity Receive

V následující tabulce jsou uvedeny vlastnosti <xref:System.ServiceModel.Activities.Receive> a popisuje, jak se používají v návrháři. Tyto vlastnosti lze upravovat v mřížce vlastností nebo na Návrhář postupu provádění ploše. Jediná požadovaná vlastnost je vlastnost <xref:System.ServiceModel.Activities.Receive.OperationName%2A>.

| Název vlastnosti | Požadováno | Použití |
|-|----------|-|
| <xref:System.Activities.Activity.DisplayName%2A> | False | Určuje popisný název aktivity <xref:System.ServiceModel.Activities.Receive>. Výchozí hodnota je Receive.<br /><br /> I když použití jiné než výchozí hodnoty pro popisný <xref:System.Activities.Activity.DisplayName%2A> není naprosto povinné, je vhodné použít takovou hodnotu. |
| <xref:System.ServiceModel.Activities.Receive.OperationName%2A> | Podmínka | Určuje název operace služby implementované touto <xref:System.ServiceModel.Activities.Receive> aktivitou. Tato vlastnost slouží k vytvoření výchozí hodnoty pro vlastnost **Action** , pokud vlastnost **Action** není explicitně nastavena. |
| <xref:System.ServiceModel.Activities.Receive.ServiceContractName%2A> | False | Určuje název kontraktu služby. Tato vlastnost slouží k seskupení operací služby do jednotlivých kontraktů služby. Všechny <xref:System.ServiceModel.Activities.Receive> aktivity, které mají stejný <xref:System.ServiceModel.Activities.Receive.ServiceContractName%2A>, jsou seskupeny do stejné kontraktu služby (typ portu WSDL). Výchozí hodnota je plně kvalifikovaný název CLR aktivity nejvyšší úrovně (kořene). |
| <xref:System.ServiceModel.Activities.Receive.Content%2A> | False | Určuje zprávu nebo parametr obsahu, který se má přijmout. Může to být buď aktivita <xref:System.ServiceModel.Activities.ReceiveMessageContent>, nebo aktivita <xref:System.ServiceModel.Activities.ReceiveParametersContent>. Upravte tuto vlastnost tak, že vyberete tlačítko se třemi tečkami vedle pole **obsah** v mřížce vlastností nebo kliknete na tlačítko **definovat...** vedle popisku **obsahu** na ploše návrháře aktivity **příjmu** . V obou zobrazeních se zobrazí dialogové okno **definice obsahu** . Další informace o tom, jak používat toto pole, najdete v tématu věnovaném [definici obsahu v dialogu](../workflow-designer/content-definition-dialog-box.md) . |
| <xref:System.ServiceModel.Activities.Receive.CorrelatesOn%2A> | False | Určuje korelace mezi aktivitami <xref:System.ServiceModel.Activities.Receive> v rámci operací služby pracovního postupu s objektem <xref:System.ServiceModel.MessageQuerySet>. Kliknutím na tlačítko se třemi tečkami vedle vlastnosti <xref:System.ServiceModel.Activities.Receive.CorrelatesOn%2A> v mřížce vlastnosti otevřete dialogové okno **definice vlastnosti CorrelatesOn** . Další informace o použití tohoto dialogového okna najdete v části [definice obsahu](../workflow-designer/content-definition-dialog-box.md) v tématu. |
| <xref:System.ServiceModel.Activities.Receive.CorrelatesWith%2A> | False | Určuje <xref:System.ServiceModel.Activities.CorrelationHandle>, který se použije ke směrování zprávy do příslušné instance pracovního postupu.<br /><br /> Kliknutím na tlačítko se třemi tečkami vedle vlastnosti <xref:System.ServiceModel.Activities.Receive.CorrelatesWith%2A> v mřížce vlastnosti otevřete dialogové okno **Editor výrazů** . Další informace o použití tohoto dialogového okna naleznete v tématu [Postupy: použití editoru výrazů](../workflow-designer/how-to-use-the-expression-editor.md) . |
| <xref:System.ServiceModel.Activities.Receive.CorrelationInitializers%2A> | False | Určuje kolekci <xref:System.ServiceModel.Activities.CorrelationInitializer> objektů, které inicializují více objektů <xref:System.ServiceModel.Activities.CorrelationHandle>, které konfigurují tuto <xref:System.ServiceModel.Activities.Receive> aktivitu v rámci pracovního postupu. Kliknutím na tlačítko se třemi tečkami vedle vlastnosti <xref:System.ServiceModel.Activities.Receive.CorrelationInitializers%2A> v mřížce vlastnosti otevřete dialogové okno **Přidat Inicializátory korelace** . Další informace o použití tohoto pole najdete v tématu věnovaném [dialogovému oknu Přidat inicializátoři CorrelationInitializers](../workflow-designer/add-correlationinitializers-dialog-box.md) . |
| <xref:System.ServiceModel.Activities.Receive.CanCreateInstance%2A> | False | Určuje hodnotu, která určuje, zda je vytvořena nová instance pracovního postupu pro zpracování zprávy, pokud zpráva nekoreluje s existující instancí pracovního postupu. Pokud je hodnota nastavená na **true**, vytvoří se nová instance pracovního postupu pro zpracování zprávy, když se zpráva nekoreluje s existující instancí pracovního postupu. |
| <xref:System.ServiceModel.Activities.Receive.KnownTypes%2A> | False | Určuje kolekci známých typů pro operaci služby implementovanou touto <xref:System.ServiceModel.Activities.Receive> aktivitou. Tato vlastnost by měla být použita společně s vlastností <xref:System.ServiceModel.Activities.Receive.SerializerOption%2A> nastavenou na hodnotu <xref:System.Runtime.Serialization.DataContractSerializer>. Pokud se používá <xref:System.Xml.Serialization.XmlSerializer>, ignoruje se.<br /><br /> Kliknutím na tlačítko se třemi tečkami vedle pole **KnownTypes** v mřížce vlastností zobrazíte dialogové okno **Editor kolekcí typů** , ve kterém můžete přidat relevantní typy. Další informace o použití tohoto pole naleznete v tématu [dialogové okno Editor kolekcí typů](../workflow-designer/type-collection-editor-dialog-box.md) . |
| <xref:System.ServiceModel.Activities.Receive.ProtectionLevel%2A> | False | Určuje <xref:System.Net.Security.ProtectionLevel> zprávy.<br /><br /> 1. <xref:System.Net.Security.ProtectionLevel> znamená pouze ověřování.<br />2. <xref:System.Net.Security.ProtectionLevel> znamená znaménka dat, která pomůžou zajistit integritu přenášených dat.<br />3. <xref:System.Net.Security.ProtectionLevel> znamená šifrování a podepsání dat, které vám pomůžou zajistit důvěrnost a integritu přenášených dat. |
| <xref:System.ServiceModel.Activities.Receive.SerializerOption%2A> | False | Určuje typ serializátoru, který se má použít pro operaci služby implementovanou aktivitou <xref:System.ServiceModel.Activities.Receive>. Výchozí hodnota je <xref:System.Runtime.Serialization.DataContractSerializer>, která serializace a deserializace instance typu do datového proudu XML nebo dokumentu, který používá zadaný kontrakt dat. @No__t_0 lze použít také v případě, že je v kódu XML vyžadováno větší řízení. |
| <xref:System.ServiceModel.Activities.Receive.Action%2A> | False | Určuje hlavičku akce zprávy. Pokud není nastavena explicitně, jeho hodnota je výchozím nastavením: `https://tempuri.org/{service contract namespace}/{service contract name}/{operation name}`. |

## <a name="see-also"></a>Viz také:

- [InitializeCorrelation](../workflow-designer/initializecorrelation-activity-designer.md)
- [CorrelationScope](../workflow-designer/correlationscope-activity-designer.md)
- [ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md)
- [Send](../workflow-designer/send-activity-designer.md)
- [SendAndReceiveReply](../workflow-designer/sendandreceivereply-template-designer.md)
- [TransactedReceiveScope](../workflow-designer/transactedreceivescope-activity-designer.md)
