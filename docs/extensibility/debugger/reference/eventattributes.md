---
title: EVENTATTRIBUTES | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- EVENTATTRIBUTES
helpviewer_keywords:
- EVENTATTRIBUTES enumeration
ms.assetid: 04db10f7-df31-4464-98e8-b3777428179e
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 60bd3296ed3c610b238abf00d90781b6e0067d72
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54953822"
---
# <a name="eventattributes"></a>EVENTATTRIBUTES
Určuje atributy události.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
enum enum_EVENTATTRIBUTES {   
   EVENT_ASYNCHRONOUS          = 0x0000,  
   EVENT_SYNCHRONOUS           = 0x0001,  
   EVENT_STOPPING              = 0x0002,  
   EVENT_ASYNC_STOP            = 0x0002,  
   EVENT_SYNC_STOP             = 0x0003,  
   EVENT_IMMEDIATE             = 0x0004,  
   EVENT_EXPRESSION_EVALUATION = 0x0008  
};  
typedef DWORD EVENTATTRIBUTES;  
```  
  
```csharp  
public enum enum_EVENTATTRIBUTES {   
   EVENT_ASYNCHRONOUS          = 0x0000,  
   EVENT_SYNCHRONOUS           = 0x0001,  
   EVENT_STOPPING              = 0x0002,  
   EVENT_ASYNC_STOP            = 0x0002,  
   EVENT_SYNC_STOP             = 0x0003,  
   EVENT_IMMEDIATE             = 0x0004,  
   EVENT_EXPRESSION_EVALUATION = 0x0008  
};  
```  
  
## <a name="members"></a>Členové  
 EVENT_ASYNCHRONOUS  
 Označuje, že událost je asynchronní a je potřeba žádná odpověď na události.  
  
 EVENT_SYNCHRONOUS  
 Označuje, že událost je synchronní; Odpovědět prostřednictvím [ContinueFromSynchronousEvent](../../../extensibility/debugger/reference/idebugengine2-continuefromsynchronousevent.md).  
  
 EVENT_STOPPING  
 Označuje, že se jedná o událostí ukončení. Musí být kombinován se buď `EVENT_ASYNCHRONOUS` nebo `EVENT_SYNCHRONOUS`.  
  
 EVENT_ASYNC_STOP  
 Označuje asynchronní zastavení událost. Aktuálně neexistuje žádná taková událost. Tento příznak je jen zástupný symbol.  
  
 EVENT_SYNC_STOP  
 Označuje událostí synchronní ukončení (kombinace `EVENT_SYNCHRONOUS` a `EVENT_STOPPING`). Tato hodnota se používá modul ladění (DE) při odesílání událostí ukončení. Odpověď se provádí prostřednictvím volání [Execute](../../../extensibility/debugger/reference/idebugprogram2-execute.md), [krok](../../../extensibility/debugger/reference/idebugprogram2-step.md), nebo [pokračovat](../../../extensibility/debugger/reference/idebugprogram2-continue.md).  
  
 EVENT_IMMEDIATE  
 Určuje události, které je odesláno okamžitě a synchronně integrovaného vývojového prostředí. Tento příznak číslo zkombinuje s další příznaky jako `EVENT_ASYNCHRONOUS`, `EVENT_SYNCHRONOUS`, nebo `EVENT_SYNC_STOP` označující typ události a fakt, že se označuje mechanismus odpověď (pokud existuje).  
  
 EVENT_EXPRESSION_EVALUATION  
 Událost je výsledkem vyhodnocení výrazu.  
  
## <a name="remarks"></a>Poznámky  
 Tyto hodnoty jsou předány v `dwAttrib` parametr [události](../../../extensibility/debugger/reference/idebugeventcallback2-event.md) metody.  
  
 Tyto hodnoty lze kombinovat pomocí logické bitové `OR`.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [ContinueFromSynchronousEvent](../../../extensibility/debugger/reference/idebugengine2-continuefromsynchronousevent.md)   
 [Event](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)