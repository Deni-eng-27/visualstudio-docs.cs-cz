---
title: IDebugObject::SetValue | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugObject::SetValue
helpviewer_keywords:
- IDebugObject::SetValue method
ms.assetid: d652e09c-cdc1-4519-8116-d7c743f5679b
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: a9c6590c45027eb3dce28e2dbac182a967e87d59
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66318951"
---
# <a name="idebugobjectsetvalue"></a>IDebugObject::SetValue
Nastaví hodnotu objektu z po sobě jdoucích řady bajtů.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT SetValue( 
   BYTE* pValue,
   UINT  nSize
);
```

```csharp
int SetValue(
   byte[] pValue,
   uint   nSize
);
```

## <a name="parameters"></a>Parametry
`pValue`\
[in] Pole bajtů představuje novou hodnotu.

`nSize`\
[in] Velikost hodnoty v bajtech.

## <a name="return-value"></a>Návratová hodnota
 V případě úspěchu vrátí hodnotu S_OK; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Hodnoty v poli se zkopírují do tohoto [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) objektu nahradí všechny existující hodnoty. Velikost je nová hodnota může být větší nebo menší než stávající hodnotu. To `IDebugObject` nemůže být referencí s hodnotou null.

## <a name="see-also"></a>Viz také:
- [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)
- [GetValue](../../../extensibility/debugger/reference/idebugobject-getvalue.md)