---
title: dwTYPE_KIND | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- dwTYPE_KIND
helpviewer_keywords:
- dwTYPE_KIND enumeration
ms.assetid: 6ff56b0f-c502-4e6c-9829-bfa05361b783
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: a9d790f12d3fc21bbae7373470746af2ebfe6dc9
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "80737190"
---
# <a name="dwtype_kind"></a>dwTYPE_KIND
Určuje, jak interpretovat typ objektu [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) .

## <a name="syntax"></a>Syntax

```cpp
enum enum_dwTYPE_KIND {
    TYPE_KIND_METADATA = 0x0001,
    TYPE_KIND_PDB      = 0x0002,
    TYPE_KIND_BUILT    = 0x0003,
};

typedef DWORD dwTYPE_KIND;
```

```csharp
public enum enum_dwTYPE_KIND {
    TYPE_KIND_METADATA = 0x0001,
    TYPE_KIND_PDB      = 0x0002,
    TYPE_KIND_BUILT    = 0x0003,
};
```

## <a name="fields"></a>Pole
`TYPE_KIND_METADATA`\
[TYPE_INFO](../../../extensibility/debugger/reference/type-info.md) sjednocení by se mělo interpretovat jako [METADATA_TYPE](../../../extensibility/debugger/reference/metadata-type.md) struktura.

`TYPE_KIND_PDB`\
`TYPE_INFO`Sjednocení by se mělo interpretovat jako struktura [PDB_TYPE](../../../extensibility/debugger/reference/pdb-type.md) .

`TYPE_KIND_BUILT`\
`TYPE_INFO`Sjednocení by se mělo interpretovat jako struktura [BUILT_TYPE](../../../extensibility/debugger/reference/built-type.md) .

## <a name="remarks"></a>Poznámky
Hodnoty tohoto výčtu se zobrazí v `dwKind` poli struktury [TYPE_INFO](../../../extensibility/debugger/reference/type-info.md) a slouží k určení, jak interpretovat `type` člena sjednocení. `TYPE_INFO`Struktura je vrácena voláním metody [GetTypeInfo](../../../extensibility/debugger/reference/idebugfield-gettypeinfo.md) .

## <a name="requirements"></a>Požadavky
Záhlaví: SH. h

Obor názvů: Microsoft. VisualStudio. Debugger. Interop

Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
- [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [TYPE_INFO](../../../extensibility/debugger/reference/type-info.md)
- [GetTypeInfo](../../../extensibility/debugger/reference/idebugfield-gettypeinfo.md)
- [METADATA_TYPE](../../../extensibility/debugger/reference/metadata-type.md)
- [PDB_TYPE](../../../extensibility/debugger/reference/pdb-type.md)
- [BUILT_TYPE](../../../extensibility/debugger/reference/built-type.md)
