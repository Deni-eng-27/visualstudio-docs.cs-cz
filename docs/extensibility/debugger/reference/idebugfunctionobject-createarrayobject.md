---
title: IDebugFunctionObject::CreateArrayObject | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugFunctionObject::CreateArrayObject
helpviewer_keywords:
- IDebugFunctionObject::CreateArrayObject method
ms.assetid: a380e53c-15f1-401f-927f-f366eea789e6
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a7ee5d4a59442238b461361522b06087650547b3
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56685141"
---
# <a name="idebugfunctionobjectcreatearrayobject"></a>IDebugFunctionObject::CreateArrayObject
Vytvoří objekt typu pole. Toto pole může obsahovat buď primitivní nebo hodnot instance objektu.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT CreateArrayObject( 
   OBJECT_TYPE    ot,
   IDebugField*   pClassField,
   DWORD          dwRank,
   DWORD          dwDims[],
   DWORD          dwLowBounds[],
   IDebugObject** ppObject
);
```

```csharp
int CreateArrayObject(
   enum_OBJECT_TYPE ot,
   IDebugField      pClassField,
   uint             dwRank,
   uint[]           dwDims,
   uint[]           dwLowBounds,
   out IDebugObject ppObject
);
```

#### <a name="parameters"></a>Parametry
 `ot`

 [in] Určuje hodnotu z [OBJECT_TYPE](../../../extensibility/debugger/reference/object-type.md) výčet určující typ nového objektu pole.

 `pClassField`

 [in] [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) objekt představující třídu objektu, pokud vytvoření instance hodnoty pole objektu. Při vytváření pole objektů primitivní, je tento parametr hodnotu null.

 `dwRank`

 [in] Pořadí nebo počet rozměrů pole.

 `dwDims`

 [in] Velikost každého rozměru pole.

 `dwLowBounds`

 [in] Počátek každé dimenze (obvykle 0 nebo 1).

 `ppObject`

 [out] Vrátí [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) objekt představující nově vytvořené pole. Ve skutečnosti se jedná [IDebugArrayObject](../../../extensibility/debugger/reference/idebugarrayobject.md) objektu.

## <a name="return-value"></a>Návratová hodnota
 V případě úspěchu vrátí hodnotu S_OK; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Volejte tuto metodu za účelem vytvoření objektu, který představuje funkci, která je reprezentována jako parametr pole [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md) rozhraní.

## <a name="see-also"></a>Viz také
- [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md)