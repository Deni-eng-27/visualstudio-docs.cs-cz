---
title: BP_COND_STYLE | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- BP_COND_STYLE
helpviewer_keywords:
- BP_COND_STYLE enumeration
ms.assetid: a93b1412-f447-48a1-af9d-38f3dbb3092f
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 2d82656e50b472712d7bed39c1a1decdc84f0242
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55025147"
---
# <a name="bpcondstyle"></a>BP_COND_STYLE
Určuje styl podmínku zarážky pro čekající a vázán zarážky.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
enum enum_BP_COND_STYLE {   
   BP_COND_NONE         = 0x0000,  
   BP_COND_WHEN_TRUE    = 0x0001,  
   BP_COND_WHEN_CHANGED = 0x0002  
};  
typedef DWORD BP_COND_STYLE;  
```  
  
```csharp  
public enum enum_BP_COND_STYLE {   
   BP_COND_NONE         = 0x0000,  
   BP_COND_WHEN_TRUE    = 0x0001,  
   BP_COND_WHEN_CHANGED = 0x0002  
};  
```  
  
## <a name="members"></a>Členové  
 BP_COND_NONE  
 Při dosažení zarážky na pozici, je vyvoláno zarážku. Není zadaná žádná podmínka zarážky.  
  
 BP_COND_WHEN_TRUE  
 Aktivuje zarážku, jen když podmíněný výraz přidružený k zarážce vyhodnocen `true`.  
  
 BP_COND_WHEN_CHANGED  
 Je aktivována zarážka pouze v případě, že hodnota podmíněný výraz přidružený k zarážce byl změněn z jeho předchozí hodnocení.  
  
## <a name="remarks"></a>Poznámky  
 Používá pro `styleCondition` člena [BP_CONDITION](../../../extensibility/debugger/reference/bp-condition.md) struktury.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [BP_CONDITION](../../../extensibility/debugger/reference/bp-condition.md)