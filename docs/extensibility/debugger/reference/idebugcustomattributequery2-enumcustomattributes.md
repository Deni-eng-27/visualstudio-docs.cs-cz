---
title: IDebugCustomAttributeQuery2::EnumCustomAttributes | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugCustomAttributeQuery2::EnumCustomAttributes
helpviewer_keywords:
- IDebugCustomAttributeQuery2::EnumCustomAttributes
ms.assetid: 94bfce74-aa3d-45f0-8e04-5715faf85217
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: aade3935a49af176220e800647e6e821054bbb48
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56710354"
---
# <a name="idebugcustomattributequery2enumcustomattributes"></a>IDebugCustomAttributeQuery2::EnumCustomAttributes
Získá enumerátor pro všechny vlastní atributy připojené k tomuto poli.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT EnumCustomAttributes( 
   IEnumDebugCustomAttributes** ppEnum
);
```

```csharp
int EnumCustomAttributes(
   out IEnumDebugCustomAttributes ppEnum
);
```

#### <a name="parameters"></a>Parametry
 `ppEnum`

 [out] Vrátí [IEnumDebugCustomAttributes](../../../extensibility/debugger/reference/ienumdebugcustomattributes.md) objekt představující seznam vlastních atributů; jinak vrátí hodnotu null, pokud neexistují žádné vlastní atributy.

## <a name="return-value"></a>Návratová hodnota
 V případě úspěchu, vrátí hodnotu S_OK nebo S_FALSE, pokud nejsou žádné vlastní atributy v tomto poli. V opačném případě vrátí kód chyby;

## <a name="remarks"></a>Poznámky
 Pole může mít několik vlastních atributů.

## <a name="see-also"></a>Viz také
- [IDebugCustomAttributeQuery2](../../../extensibility/debugger/reference/idebugcustomattributequery2.md)
- [IEnumDebugCustomAttributes](../../../extensibility/debugger/reference/ienumdebugcustomattributes.md)