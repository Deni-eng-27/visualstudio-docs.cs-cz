---
title: BP_LOCATION_CODE_ADDRESS | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: BP_LOCATION_CODE_ADDRESS
helpviewer_keywords: BP_LOCATION_CODE_ADDRESS structure
ms.assetid: 83c9da8b-19d9-4be5-b225-854543654901
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e0dc53f11dd4ba06488dbd53b9a1f4014268412d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="bplocationcodeaddress"></a>BP_LOCATION_CODE_ADDRESS
Popisuje umístění zarážek na adresu v kódu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
typedef struct _BP_LOCATION_CODE_ADDRESS {   
   BSTR bstrContext;  
   BSTR bstrModuleUrl;  
   BSTR bstrFunction;  
   BSTR bstrAddress;  
} BP_LOCATION_CODE_ADDRESS;  
```  
  
## <a name="members"></a>Členové  
 `bstrContext`  
 Kontext zarážce, obvykle název metody nebo funkce jako zaznamenané v zásobníku volání.  
  
 `bstrModuleUrl`  
 Adresa URL modul, který obsahuje zarážku.  
  
 `bstrFunction`  
 Název funkce, která obsahuje bod přerušení.  
  
 `bstrAddress`  
 Adresa zarážek, který je analyzovat tím vyhodnocení výrazu pro vytvoření vazby na [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) objektu.  
  
## <a name="remarks"></a>Poznámky  
 Tato struktura je členem skupiny [BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md) struktura jako součást spojení.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Struktury a sjednocení](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md)   
 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)