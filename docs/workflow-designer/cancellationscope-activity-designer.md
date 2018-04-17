---
title: Návrhář aktivity CancellationScope | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Statements.CancellationScope.UI
ms.assetid: 2c85d663-b219-4142-9866-7693ffd46379
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3231d62d5c961e63fa2a72374d5a1adcf50288f0
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="cancellationscope-activity-designer"></a>Návrhář aktivity CancellationScope
**CancellationScope** Návrhář aktivity se používá k vytvoření a konfigurace <xref:System.Activities.Statements.CancellationScope> aktivity.

## <a name="the-cancellationscope-activity"></a>CancellationScope aktivity
 <xref:System.Activities.Statements.CancellationScope> Aktivitu můžete zadat aktivitu pro spouštění a zrušení logiku pro danou aktivitu.

### <a name="using-the-cancellationscope-activity-designer"></a>Pomocí návrháře CancellationScope aktivity
 **CancellationScope** Návrhář aktivity naleznete v **transakce** kategorii **sada nástrojů**, který přistupuje kliknutím **sada nástrojů**  kartě [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] (případně vyberte možnost **nástrojů** z **zobrazení** nabídky nebo CTRL + ALT + X.)

 **CancellationScope** Návrhář aktivity můžete přetáhnout z **sada nástrojů** a vynechaných na [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] prostor kdekoli aktivity jsou obvykle umístěny, například jako uvnitř <xref:System.Activities.Statements.Sequence>. Tím se vytvoří <xref:System.Activities.Statements.CancellationScope> aktivitu výchozí <xref:System.Activities.Activity.DisplayName%2A> z CancellationScope. <xref:System.Activities.Activity.DisplayName%2A> Hodnota se dá upravit v hlavičce **CancellationScope** Návrhář aktivity nebo v **DisplayName** pole mřížku vlastností.

### <a name="the-cancellationscope-properties"></a>Vlastnosti CancellationScope
 Následující tabulce je zobrazena <xref:System.Activities.Statements.CancellationScope> vlastnosti a popisuje, jak se používají v návrháři. <xref:System.Activities.Activity.DisplayName%2A> Vlastnost lze upravit v tabulce vlastností, ale ostatní vlastnosti musí být upravovat na [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] prostor.

|Název vlastnosti|Požadováno|Použití|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Volitelné popisný název <xref:System.Activities.Statements.CancellationScope> aktivity. Výchozí hodnota je CancellationScope. I když <xref:System.Activities.Activity.DisplayName%2A> hodnota není nezbytně nutné, je osvědčeným postupem použít.|
|<xref:System.Activities.Statements.CancellationScope.Body%2A>|Hodnota TRUE|Určuje aktivity, pro které zrušení logiku poskytnuty. Chcete-li přidat <xref:System.Activities.Statements.CancellationScope.Body%2A> aktivity, vyřaďte aktivitu z **sada nástrojů** do **textu** pole na **CancellationScope** Návrhář aktivity s textem pomocný parametr "rozevírací Aktivity sem".|
|<xref:System.Activities.Statements.CancellationScope.CancellationHandler%2A>|Hodnota TRUE|Určuje aktivity, která se spustí v případě zrušení. Chcete-li přidat <xref:System.Activities.Statements.CancellationScope.CancellationHandler%2A> aktivity, vyřaďte aktivitu z **sada nástrojů** do **CancellationHandler** pole na **CancellationScope** Návrhář aktivity s pomocným parametrem text "Aktivity Sem přetáhněte".|

## <a name="see-also"></a>Viz také

- [Transakce](../workflow-designer/transaction-activity-designers.md)
- [CompensableActivity](../workflow-designer/compensableactivity-activity-designer.md)
- [Kompenzace](../workflow-designer/compensate-activity-designer.md)
- [Potvrďte](../workflow-designer/confirm-activity-designer.md)
- [TransactionScope](../workflow-designer/transactionscope-activity-designer.md)