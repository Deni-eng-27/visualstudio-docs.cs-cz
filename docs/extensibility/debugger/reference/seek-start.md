---
title: SEEK_START | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- SEEK_START
helpviewer_keywords:
- SEEK_START enumeration
ms.assetid: 55bd8901-626e-428b-a263-23b14417f4c6
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 55be60c35ea3af97cb9129670ef422d1a649fead
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="seekstart"></a>SEEK_START
Určuje umístění, ze kterého má začít vyhledávání v datovém proudu zpětný překlad.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
enum enum_SEEK_START {   
   SEEK_START_BEGIN       = 0x0001,  
   SEEK_START_END         = 0x0002,  
   SEEK_START_CURRENT     = 0x0003,  
   SEEK_START_CODECONTEXT = 0x0004,  
   SEEK_START_CODELOCID   = 0x0005  
};  
typedef DWORD SEEK_START;  
```  
  
```csharp  
public enum enum_SEEK_START {   
   SEEK_START_BEGIN       = 0x0001,  
   SEEK_START_END         = 0x0002,  
   SEEK_START_CURRENT     = 0x0003,  
   SEEK_START_CODECONTEXT = 0x0004,  
   SEEK_START_CODELOCID   = 0x0005  
};  
```  
  
## <a name="members"></a>Členové  
 SEEK_START_BEGIN  
 Spustí vyhledávání od začátku aktuálního dokumentu.  
  
 SEEK_START_END  
 Spustí vyhledávání na konci aktuálním dokumentu.  
  
 SEEK_START_CURRENT  
 Spustí vyhledávání na aktuální pozici aktuálního dokumentu.  
  
 SEEK_START_CODECONTEXT  
 Spustí vyhledávání v kontextu daného kódu aktuálního dokumentu.  
  
 SEEK_START_CODELOCID  
 Spustí vyhledávání v umístění identifikátor daného kódu. Identifikátory umístění kódu se získá voláním [GetCurrentLocation](../../../extensibility/debugger/reference/idebugdisassemblystream2-getcurrentlocation.md).  
  
## <a name="remarks"></a>Poznámky  
 Předat jako argument k [Seek](../../../extensibility/debugger/reference/idebugdisassemblystream2-seek.md) metoda.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [Hledat](../../../extensibility/debugger/reference/idebugdisassemblystream2-seek.md)   
 [GetCurrentLocation](../../../extensibility/debugger/reference/idebugdisassemblystream2-getcurrentlocation.md)