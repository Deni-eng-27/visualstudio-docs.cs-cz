---
title: BP_UNBOUND_REASON | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- BP_UNBOUND_REASON
helpviewer_keywords:
- BP_UNBOUND_REASON enumeration
ms.assetid: 939b6f9c-113b-471d-9f30-b03871af6285
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 65398ac0c4bde18dc772d75ceea203bdbfe3b189
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31109000"
---
# <a name="bpunboundreason"></a>BP_UNBOUND_REASON
Poskytuje důvod, proč nevázaný zarážky.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
enum enum_BP_UNBOUND_REASON {   
   BPUR_UNKNOWN           = 0x0000,  
   BPUR_CODE_UNLOADED     = 0x0002,  
   BPUR_BREAKPOINT_REBIND = 0x0003,  
   BPUR_BREAKPOINT_ERROR  = 0x0004  
};  
typedef DWORD BP_UNBOUND_REASON;  
```  
  
```csharp  
public enum enum_BP_UNBOUND_REASON {   
   BPUR_UNKNOWN           = 0x0000,  
   BPUR_CODE_UNLOADED     = 0x0002,  
   BPUR_BREAKPOINT_REBIND = 0x0003,  
   BPUR_BREAKPOINT_ERROR  = 0x0004  
};  
```  
  
## <a name="members"></a>Členové  
 BPUR_UNKNOWN  
 Důvodem neznámý.  
  
 BPUR_CODE_UNLOADED  
 Kód, který obsahuje zarážce byl odpojen.  
  
 BPUR_BREAKPOINT_REBIND  
 Zarážce má byla odrážejí do jiného umístění. To se může vyskytnout po upravit a pokračovat v operacích přesun zarážkou, nebo když zarážce je vázána na soubor s cestu, která již není platný.  
  
 BPUR_ BREAKPOINT_ERROR  
 Je zjištěna zarážce je vázán, co se v chybě. To se stane spravované zarážky, jejichž podmínky již není platný.  
  
## <a name="remarks"></a>Poznámky  
 Vrácený [getreason –](../../../extensibility/debugger/reference/idebugbreakpointunboundevent2-getreason.md) metoda.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [Getreason –](../../../extensibility/debugger/reference/idebugbreakpointunboundevent2-getreason.md)