---
title: IEnumDebugObjects | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumDebugObjects
helpviewer_keywords:
- IEnumDebugObjects interface
ms.assetid: 0950364c-6c8a-4b6c-ba37-c6aa359fa72c
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: c04409fb695613fea5d54b285946c04719fbe5b0
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "80716267"
---
# <a name="ienumdebugobjects"></a>IEnumDebugObjects
> [!IMPORTANT]
> V aplikaci Visual Studio 2015 je tento způsob implementace vyhodnocovacích vyhodnocení výrazů zastaralý. Informace o implementaci vyhodnocovacích vyhodnocení výrazů CLR naleznete v tématu [vyhodnocovací filtry výrazů CLR](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) a [Ukázka vyhodnocovacího filtru spravovaného výrazu](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).

 Toto rozhraní představuje kolekci objektů, které implementují rozhraní [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) .

## <a name="syntax"></a>Syntax

```
IEnumDebugObjects : IUnknown
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 Vyhodnocovací filtr výrazů implementuje toto rozhraní, aby poskytoval sady objektů, které implementují rozhraní [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) . Všimněte si, že se nejedná o standardní výčet modelu COM z důvodu přítomnosti metody [GetCount](../../../extensibility/debugger/reference/ienumdebugobjects-getcount.md) .

## <a name="notes-for-callers"></a>Poznámky pro volající
- [GetElements](../../../extensibility/debugger/reference/idebugarrayobject-getelements.md) vrací toto rozhraní.

## <a name="methods-in-vtable-order"></a>Metody v pořadí vtable
 Toto rozhraní implementuje následující metody.

|Metoda|Popis|
|------------|-----------------|
|[Další](../../../extensibility/debugger/reference/ienumdebugobjects-next.md)|Načte další sadu objektů [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) z výčtu.|
|[Přeskočit](../../../extensibility/debugger/reference/ienumdebugobjects-skip.md)|Přeskočí zadaný počet položek.|
|[Reset](../../../extensibility/debugger/reference/ienumdebugobjects-reset.md)|Obnoví výčet na první položku.|
|[Klonování](../../../extensibility/debugger/reference/ienumdebugobjects-clone.md)|Načte kopii aktuálního výčtu.|
|[GetCount](../../../extensibility/debugger/reference/ienumdebugobjects-getcount.md)|Načte počet položek ve výčtu.|

## <a name="remarks"></a>Poznámky
 Toto rozhraní umožňuje ladicímu stroji vytvořit výčet pro sadu objektů v poli.

## <a name="requirements"></a>Požadavky
 Záhlaví: ee. h

 Obor názvů: Microsoft. VisualStudio. Debugger. Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
- [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)
- [GetElements](../../../extensibility/debugger/reference/idebugarrayobject-getelements.md)
