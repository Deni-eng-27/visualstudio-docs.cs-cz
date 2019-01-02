---
title: Návrhář postupu provádění – Návrhář aktivity Cancellationscope
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
f1_keywords:
- System.Activities.Statements.CancellationScope.UI
ms.assetid: 2c85d663-b219-4142-9866-7693ffd46379
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 124b4d5d1b8e35611d990fd6c169a880a4e13a5c
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53872249"
---
# <a name="cancellationscope-activity-designer"></a>Návrhář aktivity CancellationScope

**CancellationScope** Návrhář aktivity se používá k vytvoření a konfigurace <xref:System.Activities.Statements.CancellationScope> aktivity.

## <a name="the-cancellationscope-activity"></a>Aktivity CancellationScope

<xref:System.Activities.Statements.CancellationScope> Aktivit vám umožní určit aktivitu pro spouštění a rušení logiku pro danou aktivitu.

### <a name="using-the-cancellationscope-activity-designer"></a>Pomocí aktivity Cancellationscope

**CancellationScope** návrháře aktivit najdete v **transakce** kategorie **nástrojů**. Chcete-li otevřít **nástrojů**, vyberte **nástrojů** kartu návrháře postupu provádění. Můžete také vybrat **nástrojů** z **zobrazení** nabídky nebo stisknutím klávesy **Ctrl**+**Alt** + **X**.

**CancellationScope** návrháře aktivit můžete přetáhnout z **nástrojů** a vyřadit na povrch návrháře postupu provádění bez ohledu na to aktivity jsou umístěny, například jako uvnitř <xref:System.Activities.Statements.Sequence>. Vyřazení **CancellationScope** vytvoří Návrhář aktivity <xref:System.Activities.Statements.CancellationScope> aktivity s výchozím <xref:System.Activities.Activity.DisplayName%2A> z CancellationScope. Upravit <xref:System.Activities.Activity.DisplayName%2A> hodnota v hlavičce **CancellationScope** návrháře aktivit. Můžete také upravit ho **DisplayName** pole mřížku vlastností.

### <a name="the-cancellationscope-properties"></a>Vlastnosti CancellationScope

Následující tabulka ukazuje <xref:System.Activities.Statements.CancellationScope> vlastnosti a popisuje, jak se používají v návrháři. <xref:System.Activities.Activity.DisplayName%2A> Vlastnost lze upravit v mřížce vlastností, ale další vlastnosti nutné upravit na plochu návrháře postupu provádění.

|Název vlastnosti|Požadováno|Použití|
|-|--------------|-|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Volitelné jméno <xref:System.Activities.Statements.CancellationScope> aktivity. Výchozí hodnota je CancellationScope. I když <xref:System.Activities.Activity.DisplayName%2A> hodnota není bezpodmínečně nutné, je osvědčeným postupem je použití jednoho.|
|<xref:System.Activities.Statements.CancellationScope.Body%2A>|Pravda|Určuje aktivity, pro které zrušení logiky poskytnuty. Chcete-li přidat <xref:System.Activities.Statements.CancellationScope.Body%2A> aktivity, rozevírací aktivitu z **nástrojů** do **text** pole na **CancellationScope** návrháře aktivit. Přidáte text nápovědy "Aktivity Sem přetáhněte".|
|<xref:System.Activities.Statements.CancellationScope.CancellationHandler%2A>|Pravda|Určuje aktivity, která se spustí, pokud je zrušení. Chcete-li přidat <xref:System.Activities.Statements.CancellationScope.CancellationHandler%2A> aktivity, rozevírací aktivitu z **nástrojů** do **CancellationHandler** pole na **CancellationScope** návrháře aktivit. Přidáte text nápovědy "Aktivity Sem přetáhněte".|

## <a name="see-also"></a>Viz také:

- [Transakce](../workflow-designer/transaction-activity-designers.md)
- [CompensableActivity](../workflow-designer/compensableactivity-activity-designer.md)
- [Compensate](../workflow-designer/compensate-activity-designer.md)
- [Confirm](../workflow-designer/confirm-activity-designer.md)
- [TransactionScope](../workflow-designer/transactionscope-activity-designer.md)