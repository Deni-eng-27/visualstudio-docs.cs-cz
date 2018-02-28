---
title: CONTEXT_INFO_FIELDS | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CONTEXT_INFO_FIELDS
helpviewer_keywords:
- CONTEXT_INFO_FIELDS enumeration
ms.assetid: ef436bd3-738e-47e8-828c-8febce752439
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 8f0316e8822706b26103f02eda1849568cf79994
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="contextinfofields"></a>CONTEXT_INFO_FIELDS
Určuje, jaké informace o kontextu paměti načtení.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
enum enum_CONTEXT_INFO_FIELDS {   
   CIF_MODULEURL =       0x00000001,  
   CIF_FUNCTION =        0x00000002,  
   CIF_FUNCTIONOFFSET =  0x00000004,  
   CIF_ADDRESS =         0x00000008,  
   CIF_ADDRESSOFFSET =   0x00000010,  
   CIF_ADDRESSABSOLUTE = 0x00000020,  
   CIF_ALLFIELDS =       0x0000003f  
};  
typedef DWORD CONTEXT_INFO_FIELDS;  
```  
  
```csharp  
public enum enum_CONTEXT_INFO_FIELDS {  
   CIF_MODULEURL =       0x00000001,  
   CIF_FUNCTION =        0x00000002,  
   CIF_FUNCTIONOFFSET =  0x00000004,  
   CIF_ADDRESS =         0x00000008,  
   CIF_ADDRESSOFFSET =   0x00000010,  
   CIF_ADDRESSABSOLUTE = 0x00000020,  
   CIF_ALLFIELDS =       0x0000003f  
};  
```  
  
## <a name="members"></a>Členové  
 CIF_MODULEURL  
 Inicializace nebo použití `bstrModuleUrl` pole z [CONTEXT_INFO](../../../extensibility/debugger/reference/context-info.md) struktury.  
  
 CIF_FUNCTION  
 Inicializace nebo použití `bstrFunction` pole z `CONTEXT_INFO` struktura.  
  
 CIF_FUNCTIONOFFSET  
 Inicializace nebo použití `posFunctionOffset` pole z `CONTEXT_INFO` struktura.  
  
 CIF_ADDRESS  
 Inicializace nebo použití `bstrAddress` pole z `CONTEXT_INFO` struktura.  
  
 CIF_ADDRESSOFFSET  
 Inicializace nebo použití `bstrAddressOffset` pole z `CONTEXT_INFO` struktura.  
  
 CIF_ALLFIELDS  
 Inicializace nebo použití všechna pole `CONTEXT_INFO` struktura.  
  
## <a name="remarks"></a>Poznámky  
 Tyto hodnoty jsou předávány parametr, který se [GetInfo](../../../extensibility/debugger/reference/idebugmemorycontext2-getinfo.md) metoda označíte, které pole [CONTEXT_INFO](../../../extensibility/debugger/reference/context-info.md) struktura mají být inicializován.  
  
 Tyto příznaky se také používají k označení které pole `CONTEXT_INFO` struktura jsou používané a platné, pokud je vrácen strukturu.  
  
 Tyto hodnoty může být kombinován s bitové operace OR.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [CONTEXT_INFO](../../../extensibility/debugger/reference/context-info.md)   
 [GetInfo](../../../extensibility/debugger/reference/idebugmemorycontext2-getinfo.md)