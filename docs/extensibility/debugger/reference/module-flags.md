---
title: MODULE_FLAGS | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- MODULE_FLAGS
helpviewer_keywords:
- MODULE_FLAGS enumeration
ms.assetid: 0e555b42-b846-4dbb-812e-8e3d11c85b2d
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 4b8080710b3225f025c329e0c5cb42331e1a059f
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66346796"
---
# <a name="moduleflags"></a>MODULE_FLAGS
Použít k popisu modulu.

## <a name="syntax"></a>Syntaxe

```cpp
enum enum_MODULE_FLAGS { 
   MODULE_FLAG_NONE        = 0x0000,
   MODULE_FLAG_SYSTEM      = 0x0001,
   MODULE_FLAG_SYMBOLS     = 0x0002,
   MODULE_FLAG_64BIT       = 0x0004,
   MODULE_FLAG_OPTIMIZED   = 0x0008,
   MODULE_FLAG_UNOPTIMIZED = 0x0010
};
typedef DWORD MODULE_FLAGS;
```

```csharp
public enum enum_MODULE_FLAGS { 
   MODULE_FLAG_NONE        = 0x0000,
   MODULE_FLAG_SYSTEM      = 0x0001,
   MODULE_FLAG_SYMBOLS     = 0x0002,
   MODULE_FLAG_64BIT       = 0x0004,
   MODULE_FLAG_OPTIMIZED   = 0x0008,
   MODULE_FLAG_UNOPTIMIZED = 0x0010
};
```

## <a name="fields"></a>Pole
 `MODULE_FLAG_NONE`\
 Určuje žádný modul.

 `MODULE_FLAG_SYSTEM`\
 Určuje modul systému.

 `MODULE_FLAG_SYMBOLS`\
 Určuje symbol modulu.

 `MODULE_FLAG_64BIT`\
 Určuje modul 64-bit.

 `MODULE_FLAG_OPTIMIZED`\
 Určuje, že byla optimalizována modulu. Tento stav se projeví v **moduly** okna.

 `MODULE_FLAG_UNOPTIMIZED`\
 Určuje, že optimalizovanou modulu. Tento stav se projeví v **moduly** okna. Toto je výchozí stav.

## <a name="remarks"></a>Poznámky
 Používá pro `m_dwModuleFlags` člena [MODULE_INFO](../../../extensibility/debugger/reference/module-info.md) struktury.

 Tyto příznaky lze kombinovat pomocí logické bitové `OR`.

## <a name="requirements"></a>Požadavky
 Záhlaví: msdbg.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také:
- [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [MODULE_INFO](../../../extensibility/debugger/reference/module-info.md)