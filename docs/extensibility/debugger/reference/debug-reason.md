---
title: DEBUG_REASON | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- DEBUG_REASON
helpviewer_keywords:
- DEBUG_REASON enumeration
ms.assetid: ad2ee898-8648-4671-9078-d32873862346
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 59954ea7e89390a5e35dbe0bfb0412da1aabc80f
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "80737419"
---
# <a name="debug_reason"></a>DEBUG_REASON
Určuje, proč byl proces spuštěn pro ladění.

## <a name="syntax"></a>Syntax

```cpp
enum enum_DEBUG_REASON {
    DEBUG_REASON_ERROR         = 0,
    DEBUG_REASON_USER_LAUNCHED = 1,
    DEBUG_REASON_USER_ATTACHED = 2,
    DEBUG_REASON_AUTO_ATTACHED = 3,
    DEBUG_REASON_CAUSALITY     = 4
};
typedef DWORD DEBUG_REASON;
```

```csharp
public enum enum_DEBUG_REASON {
    DEBUG_REASON_ERROR         = 0,
    DEBUG_REASON_USER_LAUNCHED = 1,
    DEBUG_REASON_USER_ATTACHED = 2,
    DEBUG_REASON_AUTO_ATTACHED = 3,
    DEBUG_REASON_CAUSALITY     = 4
};
```

## <a name="fields"></a>Pole
`DEBUG_REASON_ERROR`\
Objevila se nespecifická chyba (ta se používá jako výchozí podmínka, když žádný z ostatních důvodů nevyhovuje).

`DEBUG_REASON_USER_LAUNCHED`\
Proces se spustil na žádost uživatele.

`DEBUG_REASON_USER_ATTACHED`\
Již běžící proces byl připojen k uživateli.

`DEBUG_REASON_AUTO_ATTACHED`\
Proces byl automaticky připojen k době, kdy byl spuštěn.

`DEBUG_REASON_CAUSALITY`\
Proces byl spuštěn z důvodu události ladění JIT (Just *-in-time* ).

## <a name="remarks"></a>Poznámky
Vráceno z metody [GetDebugReason](../../../extensibility/debugger/reference/idebugprocess3-getdebugreason.md)

## <a name="requirements"></a>Požadavky
Záhlaví: msdbg. h

Obor názvů: Microsoft. VisualStudio. Debugger. Interop

Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
- [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [GetDebugReason](../../../extensibility/debugger/reference/idebugprocess3-getdebugreason.md)
