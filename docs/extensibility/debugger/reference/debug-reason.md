---
title: DEBUG_REASON | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: DEBUG_REASON
helpviewer_keywords: DEBUG_REASON enumeration
ms.assetid: ad2ee898-8648-4671-9078-d32873862346
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 9607afd765e1ddbc9fb2be97a0b7694aed7d493d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="debugreason"></a>DEBUG_REASON
Určuje, proč byl spuštěn proces pro ladění.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
enum enum_DEBUG_REASON {  
   DEBUG_REASON_ERROR         = 0,  
   DEBUG_REASON_USER_LAUNCHED = 1,  
   DEBUG_REASON_USER_ATTACHED = 2,  
   DEBUG_REASON_AUTO_ATTACHED = 3,  
   DEBUG_REASON_CAUSALITY     = 4  
};  
typedef DWORD DEBUG_REASON;  
```  
  
```csharp  
public enum enum_DEBUG_REASON {  
   DEBUG_REASON_ERROR         = 0,  
   DEBUG_REASON_USER_LAUNCHED = 1,  
   DEBUG_REASON_USER_ATTACHED = 2,  
   DEBUG_REASON_AUTO_ATTACHED = 3,  
   DEBUG_REASON_CAUSALITY     = 4  
};  
```  
  
#### <a name="parameters"></a>Parametry  
 DEBUG_REASON_ERROR  
 Došlo k chybě nespecifickou (používá se jako výchozí podmínku Pokud žádná z dalších důvodů, proč přizpůsobit).  
  
 DEBUG_REASON_USER_LAUNCHED  
 Proces byl spuštěn na žádost uživatele.  
  
 DEBUG_REASON_USER_ATTACHED  
 Proces spuštění již byl připojený k uživatelem.  
  
 DEBUG_REASON_AUTO_ATTACHED  
 Proces byl připojený k automaticky, pokud byl spuštěn.  
  
 DEBUG_REASON_CAUSALITY  
 Proces byl spuštěn z důvodu *pouze za běhu* ladění událostí (JIT).  
  
## <a name="remarks"></a>Poznámky  
 Vrácená z [GetDebugReason](../../../extensibility/debugger/reference/idebugprocess3-getdebugreason.md) metoda.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [GetDebugReason](../../../extensibility/debugger/reference/idebugprocess3-getdebugreason.md)