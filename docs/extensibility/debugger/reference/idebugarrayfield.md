---
title: IDebugArrayField | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugArrayField
helpviewer_keywords:
- IDebugArrayField interface
ms.assetid: 9667b0a5-4295-46cc-9388-b75c1350be15
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: dab01c1e956ced7e6894b951ab16f4ce68eb778b
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "80736290"
---
# <a name="idebugarrayfield"></a>IDebugArrayField
Toto rozhraní popisuje symbol pole nebo typ.

## <a name="syntax"></a>Syntax

```
IDebugArrayField : IDebugContainerField
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 Zprostředkovatel symbolů implementuje toto rozhraní u stejného objektu, který implementuje rozhraní [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md) . Toto rozhraní je specializace, která představuje objekty pole.

## <a name="notes-for-callers"></a>Poznámky pro volající
 Pokud parametr [GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md) vrátí příznak, použijte [QueryInterface](/cpp/atl/queryinterface) k získání tohoto rozhraní z rozhraní [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md) `FIELD_TYPE_ARRAY` .

## <a name="methods-in-vtable-order"></a>Metody v pořadí vtable
 Kromě metod v rozhraních [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) a [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md) implementuje toto rozhraní následující:

|Metoda|Popis|
|------------|-----------------|
|[GetNumberOfElements](../../../extensibility/debugger/reference/idebugarrayfield-getnumberofelements.md)|Získá počet prvků v poli.|
|[GetElementType](../../../extensibility/debugger/reference/idebugarrayfield-getelementtype.md)|Získá typ prvku v poli.|
|[GetRank](../../../extensibility/debugger/reference/idebugarrayfield-getrank.md)|Získá rozměr pole.|

## <a name="requirements"></a>Požadavky
 Záhlaví: SH. h

 Obor názvů: Microsoft. VisualStudio. Debugger. Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
- [Rozhraní poskytovatele symbolů ](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)
- [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md)
- [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)
