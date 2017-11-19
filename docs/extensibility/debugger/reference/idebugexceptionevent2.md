---
title: IDebugExceptionEvent2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugExceptionEvent2
helpviewer_keywords: IDebugExceptionEvent2 interface
ms.assetid: 53d32e59-a84b-4710-833e-c5ab08100516
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 4aa1c643a07f15f361c77c618d717cc2655277c6
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idebugexceptionevent2"></a>IDebugExceptionEvent2
V programu právě prováděné je vyvolána výjimka, modul ladění (DE) odešle toto rozhraní do správce ladicí relace (SDM).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugExceptionEvent2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 DE implementuje toto rozhraní do sestavy, že v programu laděné došlo k výjimce. [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) rozhraní musí být implementována pro stejný objekt jako toto rozhraní. Používá SDM [QueryInterface](/cpp/atl/queryinterface) k přístupu `IDebugEvent2` rozhraní.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 DE vytvoří a odešle tento objekt události tak, aby odesílaly výjimku. Událost je odeslána pomocí [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) funkce zpětného volání, který poskytl SDM při jej připojit k programu laděné.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Následující tabulka uvádí metody `IDebugExceptionEvent2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetException](../../../extensibility/debugger/reference/idebugexceptionevent2-getexception.md)|Získá podrobné informace o výjimku, která vyvolala tuto událost.|  
|[GetExceptionDescription](../../../extensibility/debugger/reference/idebugexceptionevent2-getexceptiondescription.md)|Získá čitelná pro člověka popis došlo k výjimce, která vyvolala tuto událost.|  
|[CanPassToDebuggee](../../../extensibility/debugger/reference/idebugexceptionevent2-canpasstodebuggee.md)|Určuje, zda modul ladění (DE) podporuje možnost předat tuto výjimku programu laděné při provádění pokračuje.|  
|[PassToDebuggee](../../../extensibility/debugger/reference/idebugexceptionevent2-passtodebuggee.md)|Určuje, zda výjimku by měla být předána laděné při obnoví spuštění programu, nebo pokud by měl být vymazány výjimka.|  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="remarks"></a>Poznámky  
 Před odesláním události, DE zkontroluje, pokud tato událost výjimky jmenovala first chance nebo sekundu odpovídající výjimce předchozí volání [SetException](../../../extensibility/debugger/reference/idebugengine2-setexception.md). Pokud je klasifikován jako první odpovídající výjimce `IDebugExceptionEvent2` událost je odeslána do SDM. V opačném případě je DE poskytuje aplikaci příležitost k zpracování výjimek. Pokud je k dispozici žádná obslužná rutina výjimky a výjimky určil jako sekundu odpovídající výjimce, `IDebugExceptionEvent2` událost je odeslána do SDM. Jinak je DE obnoví spuštění tohoto programu a operačního systému nebo modul runtime ošetří výjimku.  
  
## <a name="see-also"></a>Viz také  
 [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)   
 [SetException](../../../extensibility/debugger/reference/idebugengine2-setexception.md)   
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)