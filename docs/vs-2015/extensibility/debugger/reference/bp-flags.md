---
title: BP_FLAGS | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- BP_FLAGS
helpviewer_keywords:
- BP_FLAGS enumeration
ms.assetid: c45dfc74-5e7f-4f1e-a147-ab2a55dccbd0
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 7238f41e1971437caaaf3f5aa0c6939c47e27e55
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68153528"
---
# <a name="bpflags"></a>BP_FLAGS
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Poskytuje volitelné příznaky, které slouží k zadání dalších informací při nastavení zarážky.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
enum enum_BP_FLAGS {   
   BP_FLAG_NONE            = 0x0000,  
   BP_FLAG_MAP_DOCPOSITION = 0x0001,  
   BP_FLAG_DONT_STOP       = 0x0002  
};  
typedef DWORD BP_FLAGS;  
```  
  
```csharp  
public enum enum_BP_FLAGS {   
   BP_FLAG_NONE            = 0x0000,  
   BP_FLAG_MAP_DOCPOSITION = 0x0001,  
   BP_FLAG_DONT_STOP       = 0x0002  
};  
```  
  
## <a name="members"></a>Členové  
 BP_FLAG_NONE  
 Určuje příznak bez zarážek.  
  
 BP_FLAG_MAP_DOCPOSITION  
 Určuje, že ladicí stroj (DE) by měla být mapována zarážky pomocí umístění dokumentu. To se vztahuje pouze na zarážky nastavené v skript orientovaného zdrojových souborech, jako je například stránek ASP (Active Server).  
  
 BP_FLAG_DONT_STOP  
 Určuje, že zarážka by měla být zpracovány ladicího stroje, ale, že ladicí stroj nakonec by neměl zastavit existuje (to znamená, [IDebugBreakpointEvent2](../../../extensibility/debugger/reference/idebugbreakpointevent2.md) objektu události nesmí být rozesílaná). Tento příznak slouží k používá hlavně s zarážky s trasováním.  
  
## <a name="remarks"></a>Poznámky  
 Používá pro `dwFlags` člena [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md) a [BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md) struktury.  
  
 Tyto hodnoty lze kombinovat pomocí logické bitové `OR`.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md)   
 [BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md)   
 [IDebugBreakpointEvent2](../../../extensibility/debugger/reference/idebugbreakpointevent2.md)
