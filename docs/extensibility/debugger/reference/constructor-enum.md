---
title: CONSTRUCTOR_ENUM | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CONSTRUCTOR_ENUM
helpviewer_keywords:
- CONSTRUCTOR_ENUM enumeration
ms.assetid: 6d335b2c-66bc-460c-a4a6-4f3f1b697c2c
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 737b7bc5d71c33b1d148e0df7b6e7cac8c891e3a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="constructorenum"></a>CONSTRUCTOR_ENUM
Vybere různé typy konstruktory.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
typedef enum ConstructorMatchOptions {   
   crAll       = 0,  
   crNonStatic = 1,  
   crStatic    = 2  
} CONSTRUCTOR_ENUM;  
```  
  
```csharp  
public enum ConstructorMatchOptions {   
   crAll       = 0,  
   crNonStatic = 1,  
   crStatic    = 2  
};  
```  
  
## <a name="members"></a>Členové  
 crAll  
 Vybere všechny konstruktory.  
  
 crNonStatic  
 Vybere nestatické konstruktory.  
  
 crStatic  
 Vybere statické konstruktory.  
  
## <a name="remarks"></a>Poznámky  
 Předat jako argument k [EnumConstructors](../../../extensibility/debugger/reference/idebugclassfield-enumconstructors.md) metoda.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [Getreason –](../../../extensibility/debugger/reference/idebugcanstopevent2-getreason.md)