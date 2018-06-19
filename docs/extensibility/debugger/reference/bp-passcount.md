---
title: BP_PASSCOUNT | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- BP_PASSCOUNT
helpviewer_keywords:
- BP_PASSCOUNT structure
ms.assetid: 791ac175-b897-4c70-873e-240da7e0ac89
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: f7437a61688958a1346b9c638ad07e3e55dc51f5
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31110078"
---
# <a name="bppasscount"></a>BP_PASSCOUNT
Popisuje, počet a podmínky, na kterých je spouštěna podmíněné zarážky.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
typedef struct _BP_PASSCOUNT {   
   DWORD              dwPassCount;  
   BP_PASSCOUNT_STYLE stylePassCount;  
} BP_PASSCOUNT;  
```  
  
```csharp  
public struct BP_PASSCOUNT {   
   public uint dwPassCount;  
   public uint stylePassCount;  
};  
```  
  
## <a name="members"></a>Členové  
 `dwPassCount`  
 Počet předávání přes zarážce než se ohlásí ho.  
  
 `stylePassCount`  
 Hodnota z [BP_PASSCOUNT_STYLE](../../../extensibility/debugger/reference/bp-passcount-style.md) výčet, který určuje styl zarážce předat count.  
  
## <a name="remarks"></a>Poznámky  
 Tato struktura je členem skupiny [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md) struktury.  
  
 Tato struktura je také předat jako parametr, který se[SetPassCount](../../../extensibility/debugger/reference/idebugboundbreakpoint2-setpasscount.md) a[SetPassCount](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-setpasscount.md) metody.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Struktury a sjednocení](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md)   
 [SetPassCount](../../../extensibility/debugger/reference/idebugboundbreakpoint2-setpasscount.md)   
 [SetPassCount](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-setpasscount.md)   
 [BP_PASSCOUNT_STYLE](../../../extensibility/debugger/reference/bp-passcount-style.md)