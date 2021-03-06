---
title: CONTEXT_INFO_FIELDS | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CONTEXT_INFO_FIELDS
helpviewer_keywords:
- CONTEXT_INFO_FIELDS enumeration
ms.assetid: ef436bd3-738e-47e8-828c-8febce752439
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: b398e7ee549026750cbdff7b7fede8522116f346
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "80737588"
---
# <a name="context_info_fields"></a>CONTEXT_INFO_FIELDS
Určuje, jaké informace se mají načíst o kontextu paměti.

## <a name="syntax"></a>Syntax

```cpp
enum enum_CONTEXT_INFO_FIELDS {
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

## <a name="fields"></a>Pole
`CIF_MODULEURL`\
Inicializujte nebo použijte `bstrModuleUrl` pole struktury [CONTEXT_INFO](../../../extensibility/debugger/reference/context-info.md) .

`CIF_FUNCTION`\
Inicializujte nebo použijte `bstrFunction` pole `CONTEXT_INFO` struktury.

`CIF_FUNCTIONOFFSET`\
Inicializujte nebo použijte `posFunctionOffset` pole `CONTEXT_INFO` struktury.

`CIF_ADDRESS`\
Inicializujte nebo použijte `bstrAddress` pole `CONTEXT_INFO` struktury.

`CIF_ADDRESSOFFSET`\
Inicializujte nebo použijte `bstrAddressOffset` pole `CONTEXT_INFO` struktury.

`CIF_ALLFIELDS`\
Inicializujte nebo použijte všechna pole `CONTEXT_INFO` struktury.

## <a name="remarks"></a>Poznámky
Tyto hodnoty jsou předány parametr metody [GetInfo](../../../extensibility/debugger/reference/idebugmemorycontext2-getinfo.md) , který určuje, která pole [CONTEXT_INFO](../../../extensibility/debugger/reference/context-info.md) struktury mají být inicializována.

Tyto příznaky slouží také k označení toho, která pole `CONTEXT_INFO` struktury jsou použita a platná při vrácení struktury.

Tyto hodnoty mohou být kombinovány s bitovým operátorem OR.

## <a name="requirements"></a>Požadavky
Záhlaví: msdbg. h

Obor názvů: Microsoft. VisualStudio. Debugger. Interop

Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
- [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [CONTEXT_INFO](../../../extensibility/debugger/reference/context-info.md)
- [GetInfo](../../../extensibility/debugger/reference/idebugmemorycontext2-getinfo.md)
