---
title: IDebugMethodField | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugMethodField
helpviewer_keywords:
- IDebugMethodField interface
ms.assetid: a7dc9030-fc98-4cf1-b943-37a4003300b6
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 061035933e57ea4ca8e7857f68ac3d6311bae32c
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "80727058"
---
# <a name="idebugmethodfield"></a>IDebugMethodField
Toto rozhraní popisuje metodu.

## <a name="syntax"></a>Syntax

```
IDebugMethodField : IDebugContainerField
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 Zprostředkovatel symbolů implementuje toto rozhraní u stejného objektu, který implementuje rozhraní [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md) . Toto rozhraní je specializace, která prezentuje metodu.

## <a name="notes-for-callers"></a>Poznámky pro volající
 Pokud se vrátí [GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md) , použijte [QueryInterface](/cpp/atl/queryinterface) k získání tohoto rozhraní z rozhraní [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md) `FIELD_TYPE_METHOD` . Kromě toho metody, [GetPropertyGetter](../../../extensibility/debugger/reference/idebugpropertyfield-getpropertygetter.md), [GetPropertySetter](../../../extensibility/debugger/reference/idebugpropertyfield-getpropertysetter.md)a [EnumConstructors](../../../extensibility/debugger/reference/idebugclassfield-enumconstructors.md), všechny vrátí `IDebugMethodField` rozhraní.

## <a name="methods-in-vtable-order"></a>Metody v pořadí vtable
 Kromě metod v rozhraních [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) a [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md) toto rozhraní implementuje následující metody:

|Metoda|Popis|
|------------|-----------------|
|[EnumParameters](../../../extensibility/debugger/reference/idebugmethodfield-enumparameters.md)|Vytvoří enumerátor pro parametry metody.|
|[GetThis](../../../extensibility/debugger/reference/idebugmethodfield-getthis.md)|Získá ukazatel "This" objektu, který obsahuje metodu.|
|[EnumAllLocals](../../../extensibility/debugger/reference/idebugmethodfield-enumalllocals.md)|Vytvoří enumerátor pro všechny místní proměnné metody.|
|[EnumLocals](../../../extensibility/debugger/reference/idebugmethodfield-enumlocals.md)|Vytvoří enumerátor pro vybrané místní proměnné metody.|
|[IsCustomAttributeDefined](../../../extensibility/debugger/reference/idebugmethodfield-iscustomattributedefined.md)|Určuje, zda byl definován konkrétní vlastní atribut.|
|[EnumStaticLocals](../../../extensibility/debugger/reference/idebugmethodfield-enumstaticlocals.md)|Vytvoří enumerátor pro statické lokální proměnné metody.|
|[GetGlobalContainer](../../../extensibility/debugger/reference/idebugmethodfield-getglobalcontainer.md)|Získá globální kontejner metody.|
|[EnumArguments](../../../extensibility/debugger/reference/idebugmethodfield-enumarguments.md)|Vytvoří enumerátor pro typ každého argumentu, který je vyžadován pro volání metody.|

## <a name="remarks"></a>Poznámky
 Metoda může obsahovat parametry i místní proměnné.

## <a name="requirements"></a>Požadavky
 Záhlaví: SH. h

 Obor názvů: Microsoft. VisualStudio. Debugger. Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
- [Rozhraní poskytovatele symbolů ](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)
- [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md)
- [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)
