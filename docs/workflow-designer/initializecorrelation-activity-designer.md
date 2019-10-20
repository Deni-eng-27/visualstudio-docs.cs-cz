---
title: Návrhář aktivity Návrhář postupu provádění – InitializeCorrelation
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.ServiceModel.Activities.InitializeCorrelation.UI
ms.assetid: 4c54f34c-ee84-42a6-abb0-ec260c1ccb76
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 98a9a6bccb6eab2c4565a717daa897f93dbe8f53
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/19/2019
ms.locfileid: "72650228"
---
# <a name="initializecorrelation-activity-designer"></a>Návrhář aktivity InitializeCorrelation

Návrhář aktivity **InitializeCorrelation** slouží k vytvoření a konfiguraci aktivity <xref:System.ServiceModel.Activities.InitializeCorrelation>. Aktivita <xref:System.ServiceModel.Activities.InitializeCorrelation> vytváří korelaci mezi zprávami před jejich odesláním nebo přijetím.

## <a name="the-initializecorrelation-activity"></a>Aktivita InitializeCorrelation

@No__t_0 aktivita se používá k inicializaci korelací bez odeslání nebo přijetí zprávy. Při odesílání nebo přijímání zprávy se obvykle inicializuje korelace. Pokud musí být korelační zpráva navázána před odesláním nebo přijetím zprávy, použijte k inicializaci korelace <xref:System.ServiceModel.Activities.InitializeCorrelation>.

### <a name="using-the-initializecorrelation-activity-designer"></a>Pomocí návrháře aktivity InitializeCorrelation

Přístup k Návrháři aktivity **InitializeCorrelation** v kategorii **zasílání zpráv** sady **nástrojů**.

Návrhář aktivity **InitializeCorrelation** lze přetáhnout ze **sady nástrojů** a přetáhnout na Návrhář postupu provádění plochu. Vyřazení návrháře aktivit vytvoří aktivitu <xref:System.ServiceModel.Activities.InitializeCorrelation> s výchozím <xref:System.Activities.Activity.DisplayName%2A> InitializeCorrelation. @No__t_0 lze upravit v hlavičce návrháře aktivity **InitializeCorrelation** nebo v poli **DisplayName** v okně **vlastnosti** .

@No__t_0 může být určeno v poli **korelace** v okně **vlastnosti** na ploše návrháře aktivity **InitializeCorrelation** .

Chcete-li zobrazit dialogové okno **inicializovat korelaci** , kde můžete zadat popisovač korelace a páry klíč-hodnota použité k jeho inicializaci, vyberte tlačítko se třemi tečkami vedle pole **CorrelationData** v okně **vlastnosti** . Nebo vyberte Zobrazit... text nápovědy na ploše návrháře aktivity **InitializeCorrelation** Další informace o používání tohoto dialogového okna naleznete v článku [dialogové okno Editor kolekcí typů](../workflow-designer/type-collection-editor-dialog-box.md) .

### <a name="the-initializecorrelation-properties"></a>Vlastnosti InitializeCorrelation

V následující tabulce jsou uvedeny vlastnosti <xref:System.ServiceModel.Activities.InitializeCorrelation> a popisuje, jak se používají v návrháři. Tyto vlastnosti lze upravovat v okně **vlastnosti** nebo na Návrhář postupu provádění ploše.

|Název vlastnosti|Požadováno|Použití|
|-|--------------|-|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Popisný název aktivity <xref:System.ServiceModel.Activities.InitializeCorrelation>. Výchozí hodnota je InitializeCorrelation.<br /><br /> I když použití jiné než výchozí hodnoty pro popisný <xref:System.Activities.Activity.DisplayName%2A> není naprosto povinné, doporučuje se.|
|<xref:System.ServiceModel.Activities.InitializeCorrelation.Correlation%2A>|False|@No__t_0 slouží k přidružení aktivit pracovního postupu v korelaci.|
|<xref:System.ServiceModel.Activities.InitializeCorrelation.CorrelationData%2A>|False|Slovník dat korelace, který se týká zpráv instance pracovního postupu.<br /><br /> K nakonfigurování <xref:System.ServiceModel.Activities.InitializeCorrelation.CorrelationData%2A> použijte dialogové okno **inicializovat korelaci** . Další informace o tom, jak používat toto dialogové okno, najdete v článku [dialogové okno Editor kolekcí typů](../workflow-designer/type-collection-editor-dialog-box.md) .|

## <a name="see-also"></a>Viz také:

- [CorrelationScope](../workflow-designer/correlationscope-activity-designer.md)
- [Receive](../workflow-designer/receive-activity-designer.md)
- [ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md)
- [Send](../workflow-designer/send-activity-designer.md)
- [SendAndReceiveReply](../workflow-designer/sendandreceivereply-template-designer.md)
- [TransactedReceiveScope](../workflow-designer/transactedreceivescope-activity-designer.md)