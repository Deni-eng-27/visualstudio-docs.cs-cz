---
title: IDebugContainerField | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugContainerField
helpviewer_keywords:
- IDebugContainerField interface
ms.assetid: a8bbe061-c382-4fe9-a193-3f7d12216041
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a72296517a64c6dcfcb8e347fb00588504aa75a4
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "80733214"
---
# <a name="idebugcontainerfield"></a>IDebugContainerField
Toto rozhraní představuje symbol nebo typ, který je kontejnerem pro jiné symboly nebo typy.

## <a name="syntax"></a>Syntax

```
IDebugContainerField : IDebugField
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 Zprostředkovatel symbolů implementuje toto rozhraní u stejného objektu, který implementuje rozhraní [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) . Toto rozhraní je také základní třídou pro všechna rozhraní, která reprezentují kontejnery.

## <a name="notes-for-callers"></a>Poznámky pro volající
 Mnoho metod v mnoha rozhraních vrací toto rozhraní. Vzhledem k tomu, že se jedná o základní třídu pro všechny kontejnery, lze z tohoto rozhraní získat více specializovaných rozhraní pomocí [QueryInterface](/cpp/atl/queryinterface). Mezi taková rozhraní patří [IDebugArrayField](../../../extensibility/debugger/reference/idebugarrayfield.md), [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md), [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md)a [IDebugPropertyField](../../../extensibility/debugger/reference/idebugpropertyfield.md).

## <a name="methods-in-vtable-order"></a>Metody v pořadí vtable
 Kromě metod v rozhraní [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) implementuje toto rozhraní následující metodu:

|Metoda|Popis|
|------------|-----------------|
|[EnumFields](../../../extensibility/debugger/reference/idebugcontainerfield-enumfields.md)|Vytvoří enumerátor pro pole kontejneru.|

## <a name="remarks"></a>Poznámky
 Pole (kontejnery pro proměnné), třídy (kontejnery pro metody a proměnné) a metody (kontejnery pro parametry a lokální proměnné) jsou všechny příklady kontejnerů.

## <a name="requirements"></a>Požadavky
 Záhlaví: SH. h

 Obor názvů: Microsoft. VisualStudio. Debugger. Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
- [Rozhraní poskytovatele symbolů ](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)
- [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)
