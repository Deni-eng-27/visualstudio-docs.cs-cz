---
title: "Volat zásobník vyhodnocení | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], call stack evaluation
- call stacks, evaluation
ms.assetid: 373d6b49-0459-4cce-816e-05745a44fe49
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: fddbe370362eb30dd9560e51574847d808c126fd
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="call-stack-evaluation"></a>Vyhodnocení zásobník volání
Chcete-li zobrazit rámce zásobníku zásobníku volání při režimu pozastavení, je nutné implementovat [EnumFrameInfo](../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md) metoda.  
  
## <a name="methods-for-evaluation"></a>Metody pro vyhodnocení  
 Pro modul jednoduché ladění (DE) může být pouze jeden rámce zásobníku. Během režimu pozastavení prozkoumat rámce zásobníku, je nutné implementovat tyto metody [IDebugStackFrame2](../../extensibility/debugger/reference/idebugstackframe2.md).  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetCodeContext](../../extensibility/debugger/reference/idebugstackframe2-getcodecontext.md)|Získá kontext kód pro rámce zásobníku. Kontext kódu představuje aktuální ukazatel instrukce v rámci zásobníku.|  
|[GetDocumentContext](../../extensibility/debugger/reference/idebugstackframe2-getdocumentcontext.md)|Získá kontext dokumentu pro rámce zásobníku. Představuje kontext dokumentu aktuální umístění ve zdrojovém kódu pro rámce zásobníku. Vyžaduje se pro zobrazení zdrojového kódu, když se zastavil v programu.|  
  
 Tyto metody vyžadují implementace několik kontext související rozhraní a metody. Proto je nutné implementovat [GetDocumentContext](../../extensibility/debugger/reference/idebugcodecontext2-getdocumentcontext.md) metoda a tyto metody [IDebugDocumentContext2](../../extensibility/debugger/reference/idebugdocumentcontext2.md).  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetStatementRange](../../extensibility/debugger/reference/idebugdocumentcontext2-getstatementrange.md)|Získá soubor příkaz rozsahu kontextu dokumentu.|  
  
 Výčet kontexty kódu, je nutné implementovat všechny metody [IEnumDebugCodeContexts2](../../extensibility/debugger/reference/ienumdebugcodecontexts2.md).  
  
## <a name="see-also"></a>Viz také  
 [Řízení provádění a vyhodnocení stavu](../../extensibility/debugger/execution-control-and-state-evaluation.md)