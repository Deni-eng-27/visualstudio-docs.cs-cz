---
title: IDebugField | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugField
helpviewer_keywords:
- IDebugField interface
ms.assetid: adecdd1c-b1b9-4027-92da-74cbe910636f
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 80def3f9c3d270ebd6f2217f6ce39f07ef27b119
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66337524"
---
# <a name="idebugfield"></a>IDebugField
Toto rozhraní představuje pole, to znamená, popis symbol nebo typu.

## <a name="syntax"></a>Syntaxe

```
IDebugField : IUnknown
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 Poskytovatel symbolů implementuje toto rozhraní jako základní třída pro všechna pole.

## <a name="notes-for-callers"></a>Poznámky pro volající
 Toto rozhraní je základní třída pro všechna pole. Na základě návratové hodnoty [GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md), toto rozhraní může vrátit více specializované rozhraní pomocí [QueryInterface](/cpp/atl/queryinterface). Kromě toho mnoho rozhraní vrátit `IDebugField` objekty z různých metod.

## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí
 V následující tabulce jsou uvedeny metody objektu `IDebugField`.

|Metoda|Popis|
|------------|-----------------|
|[GetInfo](../../../extensibility/debugger/reference/idebugfield-getinfo.md)|Získá zobrazitelný informací o symbolu nebo typu.|
|[GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md)|Získá druh typu pole.|
|[GetType](../../../extensibility/debugger/reference/idebugfield-gettype.md)|Získá typ pole.|
|[GetContainer](../../../extensibility/debugger/reference/idebugfield-getcontainer.md)|Získá kontejner pole.|
|[GetAddress](../../../extensibility/debugger/reference/idebugfield-getaddress.md)|Získá adresu pole.|
|[GetSize](../../../extensibility/debugger/reference/idebugfield-getsize.md)|Získá velikost pole, v bajtech.|
|[GetExtendedInfo](../../../extensibility/debugger/reference/idebugfield-getextendedinfo.md)|Získá rozšířené informace o pole.|
|[Equal](../../../extensibility/debugger/reference/idebugfield-equal.md)|Porovná dvě pole.|
|[GetTypeInfo](../../../extensibility/debugger/reference/idebugfield-gettypeinfo.md)|Získá typ nezávislé na informace o symbolu nebo typu.|

## <a name="remarks"></a>Poznámky
 Jazyk C odpovídá typu `typedef`.

 V následujícím příkladu jazyka C++ `weather` je typem třídy a `sunny` a `stormy` jsou symboly:

```cpp
class weather;
weather sunny;
weather stormy;
```

 Zda symbol představuje pole nebo typu se dají určit pomocí volání [GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md) a podíváte [FIELD_KIND](../../../extensibility/debugger/reference/field-kind.md) výsledek. Pokud `FIELD_KIND_TYPE` bit nastaven, pole je typ a pokud `FIELD_KIND_SYMBOL` bit nastaven, je třeba otazník.

## <a name="requirements"></a>Požadavky
 Záhlaví: sh.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také:
- [Rozhraní poskytovatele symbolů ](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)