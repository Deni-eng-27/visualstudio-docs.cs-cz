---
title: PROCESS_INFO_FIELDS | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- PROCESS_INFO_FIELDS
helpviewer_keywords:
- PROCESS_INFO_FIELDS enumeration
ms.assetid: 0d9cc345-3d3a-44d8-ae15-a67acb97a828
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 3376db379e4e911bcaa8e865a16c63d1251229f6
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31126383"
---
# <a name="processinfofields"></a>PROCESS_INFO_FIELDS
Zadat, jaký druh informací k načtení procesu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
enum enum_PROCESS_INFO_FIELDS {   
   PIF_FILE_NAME             = 0x00000001,  
   PIF_BASE_NAME             = 0x00000002,  
   PIF_TITLE                 = 0x00000004,  
   PIF_PROCESS_ID            = 0x00000008,  
   PIF_SESSION_ID            = 0x00000010,  
   PIF_ATTACHED_SESSION_NAME = 0x00000020,  
   PIF_CREATION_TIME         = 0x00000040,  
   PIF_FLAGS                 = 0x00000080,  
   PIF_ALL                   = 0x000000ff  
};  
typedef DWORD PROCESS_INFO_FIELDS;  
```  
  
```csharp  
public enum enum_PROCESS_INFO_FIELDS {   
   PIF_FILE_NAME             = 0x00000001,  
   PIF_BASE_NAME             = 0x00000002,  
   PIF_TITLE                 = 0x00000004,  
   PIF_PROCESS_ID            = 0x00000008,  
   PIF_SESSION_ID            = 0x00000010,  
   PIF_ATTACHED_SESSION_NAME = 0x00000020,  
   PIF_CREATION_TIME         = 0x00000040,  
   PIF_FLAGS                 = 0x00000080,  
   PIF_ALL                   = 0x000000ff  
};  
```  
  
## <a name="members"></a>Členové  
 PIF_FILE_NAME  
 Inicializace nebo použití `bstrFileName` pole z [PROCESS_INFO](../../../extensibility/debugger/reference/process-info.md) struktury.  
  
 PIF_BASE_NAME  
 Inicializace nebo použití `bstrBaseName` pole z `PROCESS_INFO` struktura.  
  
 PIF_TITLE  
 Inicializace nebo použití `bstrTitle` pole z `PROCESS_INFO` struktura.  
  
 PIF_PROCESS_ID  
 Inicializace nebo použití `ProcessId` pole z `PROCESS_INFO` struktura.  
  
 PIF_SESSION_ID  
 Inicializace nebo použití `dwSessionId` pole z `PROCESS_INFO` struktura.  
  
 PIF_ATTACHED_SESSION_NAME  
 Inicializace nebo použití `bstrAttachedSessionName` pole z `PROCESS_INFO` struktura.  
  
 PIF_CREATION_TIME  
 Inicializace nebo použití `CreationTime` pole z `PROCESS_INFO` struktura.  
  
 PIF_FLAGS  
 Inicializace nebo použití `Flags` pole z `PROCESS_INFO` struktura.  
  
 PIF_ALL  
 Vyplní všechna pole.  
  
## <a name="remarks"></a>Poznámky  
 Předaný [GetInfo](../../../extensibility/debugger/reference/idebugprocess2-getinfo.md) metoda označíte, které pole [PROCESS_INFO](../../../extensibility/debugger/reference/process-info.md) struktura mají být inicializován.  
  
 Používat i v `Fields` pole z `PROCESS_INFO` struktura označuje pole, která je platná a použitá.  
  
 Tyto příznaky mohou být kombinovány s bitové `OR`.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [PROCESS_INFO](../../../extensibility/debugger/reference/process-info.md)