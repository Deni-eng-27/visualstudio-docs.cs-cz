---
title: NATIVE_ADDRESS | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- NATIVE_ADDRESS
helpviewer_keywords:
- NATIVE_ADDRESS structure
ms.assetid: 7a0cd085-bfc8-45cc-a3d4-4459070e207a
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 7d7d061d7cd60444a523d5764c30b7ff538faefe
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62913766"
---
# <a name="nativeaddress"></a>NATIVE_ADDRESS

Tato struktura představuje nativní adresu.

## <a name="syntax"></a>Syntaxe

```cpp
typedef struct _tagNATIVE_ADDRESS {
    DWORD unknown;
} NATIVE_ADDRESS;
```

```csharp
public struct NATIVE_ADDRESS {
    public uint unknown;
}
```

## <a name="terms"></a>Podmínky

`unknown`

Nativní adresu (význam tohoto závisí na modul runtime a operačního systému).

## <a name="remarks"></a>Poznámky

Tato struktura je součástí sjednocení v [DEBUG_ADDRESS_UNION](../../../extensibility/debugger/reference/debug-address-union.md) strukturu, kdy `dwKind` pole `DEBUG_ADDRESS_UNION` struktura je nastavena na `ADDRESS_KIND_NATIVE` (hodnotu z [ADDRESS_KIND](../../../extensibility/debugger/reference/address-kind.md) výčet).

## <a name="requirements"></a>Požadavky

Záhlaví: sh.h

Obor názvů: Microsoft.VisualStudio.Debugger.Interop

Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také:

- [Struktury a sjednocení](../../../extensibility/debugger/reference/structures-and-unions.md)
- [DEBUG_ADDRESS_UNION](../../../extensibility/debugger/reference/debug-address-union.md)
