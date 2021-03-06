---
title: IDebugBreakpointUnboundEvent2 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugBreakpointUnboundEvent2
helpviewer_keywords:
- IDebugBreakpointUnboundEvent2
ms.assetid: 6b1e1863-0c64-4d85-8ab9-aface522fdea
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 1e1d15936316d08a712e3d6f3fdc7a3a73be613d
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "80734636"
---
# <a name="idebugbreakpointunboundevent2"></a>IDebugBreakpointUnboundEvent2
Toto rozhraní oznamuje správci ladění relace (SDM), že vázaná zarážka byla nevázaná od načteného programu.

## <a name="syntax"></a>Syntax

```
IDebugBreakpointUnboundEvent2 : IUnknown
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 Ladicí stroj (DE) implementuje toto rozhraní jako součást podpory zarážek. Rozhraní [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) se musí implementovat na stejný objekt jako toto rozhraní (SDM používá pro přístup k rozhraní [QueryInterface](/cpp/atl/queryinterface) `IDebugEvent2` .).

## <a name="notes-for-callers"></a>Poznámky pro volající
 DE vytvoří a pošle tento objekt události, když je vázaná zarážka nevázaná. Událost se posílá pomocí funkce zpětného volání [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) , kterou poskytuje SDM, když je připojená k laděnému programu.

## <a name="methods-in-vtable-order"></a>Metody v pořadí vtable
 V následující tabulce jsou uvedeny metody `IDebugBreakpointUnboundEvent2` .

|Metoda|Popis|
|------------|-----------------|
|[GetBreakpoint](../../../extensibility/debugger/reference/idebugbreakpointunboundevent2-getbreakpoint.md)|Získá zarážku, která se stala nevázanou.|
|[GetReason](../../../extensibility/debugger/reference/idebugbreakpointunboundevent2-getreason.md)|Získá důvod, proč byla zarážka nevázaná.|

## <a name="remarks"></a>Poznámky
 Při ladění knihovny DLL nebo třídy ladění musí být všechny zarážky, které byly vázány na kód v tomto modulu, odpojeny od laděného programu. `IDebugBreakpointUnboundEvent2`Pro každou nevázanou zarážku se pošle.

## <a name="requirements"></a>Požadavky
 Záhlaví: msdbg. h

 Obor názvů: Microsoft. VisualStudio. Debugger. Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
- [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)
- [IDebugBoundBreakpoint2](../../../extensibility/debugger/reference/idebugboundbreakpoint2.md)
- [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)
