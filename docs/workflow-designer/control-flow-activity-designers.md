---
title: "Řízení toku návrháře aktivit | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: ba74af23-5398-4e62-bd90-c50612e3bfef
caps.latest.revision: "7"
author: ErikRe
ms.author: erikre
manager: erikre
ms.openlocfilehash: 45ffc19d3ede7af9d32e4599f17ecde9bd097bb7
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="control-flow-activity-designers"></a>Návrháře aktivit toku řízení
[!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)]zahrnuje několik poskytované systémem aktivit, které můžete použít při vytváření vaše pracovní postupy. Tato část obsahuje poskytované systémem aktivity použít k řízení toku v pracovním postupu. V následujících tématech popisují tyto aktivity a poskytují pokyny o tom, jak je používat.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [DoWhile](../workflow-designer/dowhile-activity-designer.md)  
 Provádí aktivity obsažené v jeho textu alespoň jednou, dokud je zadaná podmínka vyhodnocena jako **true**.  
  
 [ForEach\<T >](http://msdn.microsoft.com/en-us/a680cddd-2760-497a-b27b-c023fcbc6f33)  
 Provádí aktivity obsažené v jeho text pro každou položku v zadané kolekci.  
  
 [Pokud](../workflow-designer/if-activity-designer.md)  
 Vyhodnocuje podmínku a provede aktivitu v závislosti na výsledky tohoto vyhodnocení.  
  
 [Paralelní](../workflow-designer/parallel-activity-designer.md)  
 Kolekce podřízených aktivit provádí současně.  
  
 [ParallelForEach\<T >](../workflow-designer/parallelforeach-t-activity-designer.md)  
 Vytvoří výčet prvků kolekce a spouští paralelně příkazu embedded pro každý prvek kolekce  
  
 [Vyberte](../workflow-designer/pick-activity-designer.md)  
 Spustí jeden z několika větve v odpovědi na některé události, která poskytuje řízení toku na základě událostí.  
  
 [PickBranch](../workflow-designer/pickbranch-activity-designer.md)  
 Poskytuje potenciální cesty provádění v rámci <xref:System.Activities.Statements.Pick> aktivity.  
  
 [Pořadí](../workflow-designer/sequence-activity-designer.md)  
 Obsahuje kolekci seřazené podřízené aktivit, které se provede v pořadí.  
  
 [Přepínač\<T >](http://msdn.microsoft.com/en-us/ce1aa634-c4db-4475-a1c8-a88478a57212)  
 Vyhodnotí zadaný výraz a provádí aktivity z kolekce aktivit, jejichž přidružené klíč odpovídá hodnotě získané z vyhodnocení.  
  
 [Chvíli](../workflow-designer/while-activity-designer.md)  
 Provádí aktivity obsažené v jeho obsahu, když je zadaná podmínka vyhodnocena jako **true**.  
  
## <a name="reference"></a>Odkaz  
 <xref:System.Activities.Activity>  
  
 <xref:System.Activities.Statements.DoWhile>  
  
 <xref:System.Activities.Statements.ForEach%601>  
  
 <xref:System.Activities.Statements.If>  
  
 <xref:System.Activities.Statements.Parallel>  
  
 <xref:System.Activities.Statements.ParallelForEach%601>  
  
 <xref:System.Activities.Statements.Pick>  
  
 <xref:System.Activities.Statements.PickBranch>  
  
 <xref:System.Activities.Statements.Sequence>  
  
 <xref:System.Activities.Statements.Switch%601>  
  
 <xref:System.Activities.Statements.While>  
  
## <a name="related-sections"></a>Související oddíly  
 U jiných typů návrháře aktivit najdete v následujících tématech.  
  
 [Pomocí návrháře aktivit](../workflow-designer/using-the-activity-designers.md)  
  
 [Vývojový diagram](../workflow-designer/flowchart-activity-designers.md)  
  
 [Zasílání zpráv](../workflow-designer/messaging-activity-designers.md)  
  
 [Modul runtime](../workflow-designer/runtime-activity-designers.md)  
  
 [Primitivní elementy.](../workflow-designer/primitives-activity-designers.md)  
  
 [Transakce](../workflow-designer/transaction-activity-designers.md)  
  
 [Kolekce](../workflow-designer/collection-activity-designers.md)  
  
 [Zpracování chyb](../workflow-designer/error-handling-activity-designers.md)  
  
## <a name="external-resources"></a>Externí zdroje  
 [Pomocí návrháře aktivit](../workflow-designer/using-the-activity-designers.md)