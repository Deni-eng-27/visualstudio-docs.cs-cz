---
title: BP_LOCATION_CODE_ADDRESS | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- BP_LOCATION_CODE_ADDRESS
helpviewer_keywords:
- BP_LOCATION_CODE_ADDRESS structure
ms.assetid: 83c9da8b-19d9-4be5-b225-854543654901
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: e90801f17690b48ba82e9fa80fba345e206c50b2
ms.sourcegitcommit: 752f03977f45169585e407ef719450dbe219b7fc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/15/2019
ms.locfileid: "56315921"
---
# <a name="bplocationcodeaddress"></a>BP_LOCATION_CODE_ADDRESS
Popisuje umístění zarážky na adrese v kódu.

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
Kontext k zarážce, obvykle název metody nebo funkce jako zobrazené v zásobníku volání.

`bstrModuleUrl`  
Adresa URL modulu, který obsahuje zarážku.

`bstrFunction`  
Název funkce, která obsahuje zarážku.

`bstrAddress`  
Adresa zarážky, které je analyzován podle vyhodnocovače výrazů pro vytvoření vazby na [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) objektu.

## <a name="remarks"></a>Poznámky
Tato struktura je členem skupiny [BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md) struktury v rámci sjednocení.

## <a name="requirements"></a>Požadavky
Záhlaví: msdbg.h

Obor názvů: Microsoft.VisualStudio.Debugger.Interop

Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
[Struktury a sjednocení](../../../extensibility/debugger/reference/structures-and-unions.md)  
[BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md)  
[IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)
