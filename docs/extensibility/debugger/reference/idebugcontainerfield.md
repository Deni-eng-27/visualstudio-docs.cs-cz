---
title: IDebugContainerField | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugContainerField
helpviewer_keywords:
- IDebugContainerField interface
ms.assetid: a8bbe061-c382-4fe9-a193-3f7d12216041
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: c93113f89c11e787a23cc57dfbebcce882125091
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62922283"
---
# <a name="idebugcontainerfield"></a>IDebugContainerField
Toto rozhraní představuje symbol nebo typ, který je kontejnerem pro další symboly nebo typy.

## <a name="syntax"></a>Syntaxe

```
IDebugContainerField : IDebugField
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 Poskytovatel symbolů implementuje na stejný objekt, který implementuje toto rozhraní [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) rozhraní. Toto rozhraní je také základní třída pro všechna rozhraní, které představují kontejnery.

## <a name="notes-for-callers"></a>Poznámky pro volající
 Mnoho metod na mnoho rozhraní vrátí toto rozhraní. Protože je to základní třída pro všechny kontejnery, více specializované rozhraní můžete získat z tohoto rozhraní pomocí [QueryInterface](/cpp/atl/queryinterface). Taková rozhraní pro zahrnují [IDebugArrayField](../../../extensibility/debugger/reference/idebugarrayfield.md), [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md), [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md), a [IDebugPropertyField](../../../extensibility/debugger/reference/idebugpropertyfield.md).

## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí
 Kromě metod na [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) rozhraní, toto rozhraní implementuje následující metodu:

|Metoda|Popis|
|------------|-----------------|
|[EnumFields](../../../extensibility/debugger/reference/idebugcontainerfield-enumfields.md)|Vytvoří čítač pro pole kontejneru.|

## <a name="remarks"></a>Poznámky
 Pole (kontejnery pro proměnné), (kontejnery pro metody a proměnné) třídy a metody (kontejnery pro místní proměnné a parametry) jsou všechny příklady kontejnerů.

## <a name="requirements"></a>Požadavky
 Záhlaví: sh.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
- [Rozhraní poskytovatele symbolů ](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)
- [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)