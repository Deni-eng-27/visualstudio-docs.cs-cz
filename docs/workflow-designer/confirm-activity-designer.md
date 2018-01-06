---
title: "Potvrďte Návrhář aktivity | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: System.Activities.Statements.Confirm.UI
ms.assetid: c753b67b-b0e7-462a-bb4e-ba8db04a078d
caps.latest.revision: "5"
author: ErikRe
ms.author: erikre
manager: erikre
ms.workload: multiple
ms.openlocfilehash: 51e44d98aaec929f1194420227a6a3871dc4f2ad
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="confirm-activity-designer"></a>Potvrďte Návrhář aktivity
**Potvrdit** Návrhář aktivity se používá k vytvoření a konfigurace <xref:System.Activities.Statements.Confirm> aktivity.  
  
## <a name="the-confirm-activity"></a>Potvrzení aktivity  
 <xref:System.Activities.Statements.Confirm> Explicitně vyvolá aktivitu <xref:System.Activities.Statements.CompensableActivity.ConfirmationHandler%2A> pro aktivitu součástí <xref:System.Activities.Statements.CompensableActivity>. Pokud <xref:System.Activities.Statements.Confirm> aktivity se nepoužívá v rámci <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A>, <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A>, nebo <xref:System.Activities.Statements.CompensableActivity.ConfirmationHandler%2A> z <xref:System.Activities.Statements.CompensableActivity>, pak je nutné zadat <xref:System.Activities.Statements.Confirm.Target%2A> vlastnost.  
  
 <xref:System.Activities.Statements.CompensationToken> Určeným elementem <xref:System.Activities.Statements.Compensate.Target%2A> poskytuje prostředky ke explicitně potvrdit nebo odpovídajícím způsobem <xref:System.Activities.Statements.CompensableActivity> po <xref:System.Activities.Statements.CompensableActivity.Body%2A> z <xref:System.Activities.Statements.CompensableActivity> bylo úspěšně dokončeno.  
  
### <a name="using-the-confirm-activity-designer"></a>Pomocí Potvrďte Návrhář aktivity  
 **Potvrdit** Návrhář aktivity naleznete v **transakce** kategorii **sada nástrojů**, který přistupuje kliknutím **sady nástrojů**karty na levé straně [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] (případně vyberte možnost **nástrojů** z **zobrazení** nabídky nebo CTRL + ALT + X.)  
  
 **Potvrdit** Návrhář aktivity můžete přetáhnout z **sada nástrojů** a vynechaných na [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] prostor kdekoli aktivity jsou obvykle umístěny, například jako uvnitř <xref:System.Activities.Statements.Sequence>. Tím se vytvoří <xref:System.Activities.Statements.Confirm> aktivitu výchozí <xref:System.Activities.Activity.DisplayName%2A> o potvrzení. <xref:System.Activities.Activity.DisplayName%2A> Hodnota může být buď v hlavičce upravit **potvrdit** Návrhář aktivity nebo v **DisplayName** pole mřížku vlastností.  
  
### <a name="the-confirm-properties"></a>Potvrzení vlastnosti  
 Následující tabulce je zobrazena <xref:System.Activities.Statements.Confirm> vlastnosti a popisuje, jak se používají v návrháři. <xref:System.Activities.Activity.DisplayName%2A> Vlastnost lze upravit v mřížce vlastnost nebo na [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] prostor, ale <xref:System.Activities.Statements.Confirm.Target%2A> vlastnost musí upravit v tabulce vlastností.  
  
|Název vlastnosti|Požadováno|Použití|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|Určuje nepovinné popisný název <xref:System.Activities.Statements.CancellationScope> aktivity. Výchozí hodnota je potvrdit.|  
|<xref:System.Activities.Statements.Confirm.Target%2A>|Hodnota TRUE|Určuje, <xref:System.Activities.InArgument%601> obsahující <xref:System.Activities.Statements.CompensationToken> pro tento <xref:System.Activities.Statements.Confirm> aktivity.|  
  
## <a name="see-also"></a>Viz také  
 [Transakce](../workflow-designer/transaction-activity-designers.md)   
 [CancellationScope](../workflow-designer/cancellationscope-activity-designer.md)   
 [CompensableActivity](../workflow-designer/compensableactivity-activity-designer.md)   
 [Kompenzace](../workflow-designer/compensate-activity-designer.md)   
 [TransactionScope](../workflow-designer/transactionscope-activity-designer.md)