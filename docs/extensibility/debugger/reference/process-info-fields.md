---
title: PROCESS_INFO_FIELDS | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: PROCESS_INFO_FIELDS
helpviewer_keywords: PROCESS_INFO_FIELDS enumeration
ms.assetid: 0d9cc345-3d3a-44d8-ae15-a67acb97a828
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e5732b287512cb14ab885619799d0c885f69b791
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
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
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [PROCESS_INFO](../../../extensibility/debugger/reference/process-info.md)