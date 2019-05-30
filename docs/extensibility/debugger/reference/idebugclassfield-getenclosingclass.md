---
title: IDebugClassField::GetEnclosingClass | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugClassField::GetEnclosingClass
helpviewer_keywords:
- IDebugClassField::GetEnclosingClass method
ms.assetid: a0c12e3c-9ea0-4dfb-9e45-8cea18725022
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 6927a63241e2f2794fb5c70945962e00a1676431
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66329502"
---
# <a name="idebugclassfieldgetenclosingclass"></a>IDebugClassField::GetEnclosingClass
Získá třídu, která obklopuje této třídy.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetEnclosingClass(
    IDebugClassField** ppClassField
);
```

```csharp
int GetEnclosingClass(
    out IDebugClassField ppClassField
);
```

## <a name="parameters"></a>Parametry
`ppClassField`\
[out] Vrátí [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md) třídy představující nadřazený objekt. Vrátí hodnotu null, pokud neexistuje žádné nadřazené třídy.

## <a name="return-value"></a>Návratová hodnota
V případě úspěchu vrátí hodnotu S_OK; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
Pokud třída představovaného tímto rozhraním [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md) objektu je vnořená třída, pak bude `ppClassField` vrátí parametr `IDebugClassField` třídy představující nadřazený objekt. Například při této definici třídy:

```
class RootClass {
    class NestedClass { }
};
```

Volání `GetEnclosingClass` metodu `IDebugClassField` objekt představující `NestedClass` třídy vrátí `IDebugClassField` objekt představující třídu `RootClass`.

## <a name="see-also"></a>Viz také:
- [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)
