---
title: IDebugBinder::ResolveRuntimeType | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugBinder::ResolveRuntimeType
helpviewer_keywords:
- IDebugBinder::ResolveRuntimeType method
ms.assetid: 6456ab3e-1c03-4f3c-91f9-16797ab7f5e7
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: b2954b5f2a1ac4dd14485a1b924423ba53fddcb7
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66315167"
---
# <a name="idebugbinderresolveruntimetype"></a>IDebugBinder::ResolveRuntimeType
Tato metoda určí run-time typu objektu.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT ResolveRuntimeType( 
   IDebugObject* pObject,
   IDebugField** ppResolved
);
```

```csharp
int ResolveRuntimeType(
   IDebugObject     pObject,
   out IDebugField  ppResolved
);
```

## <a name="parameters"></a>Parametry
`pObject`\
[in] [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) vyřešit.

`ppResolved`\
[out] Vrátí typ objektu jako [IDebugField](../../../extensibility/debugger/reference/idebugfield.md).

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Za běhu typ objektu není vždy znám v době kompilace. Například pomocí polymorfismus, argument může být předán funkci jako její základní třídě, jako je například třída tlačítek. Skutečný argument může být odvozené třídy, jako je například třída tlačítek přepínače.

## <a name="see-also"></a>Viz také:
- [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md)
- [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)
- [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)