---
title: IDebugObject2::IsUserData | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugObject2::IsUserData
helpviewer_keywords:
- IDebugObject2::IsUserData method
ms.assetid: 6ffa0d0e-f742-496d-acc7-db74c248bc45
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 94c3f6adc9dd75e1ed4ecc4c5fd7f37635099566
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66317242"
---
# <a name="idebugobject2isuserdata"></a>IDebugObject2::IsUserData
Určuje, zda objekt představuje uživatelská data.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT IsUserData(
   BOOL* pfUser
);
```

```csharp
int IsUserData(
   out int pfUser
);
```

## <a name="parameters"></a>Parametry
`pfUser`\
[out] Vrátí nenulovou hodnotu (`TRUE`), pokud objekt představuje data uživatele; hodnotu (`FALSE`) Pokud tomu tak není.

## <a name="return-value"></a>Návratová hodnota
 V případě úspěchu vrátí hodnotu S_OK; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Uživatelská data je libovolný objekt, který je součástí modulu určený jako JustMyCode (uživatelem konfigurovatelné možnost, která označuje modul jako uživatelského kódu a je proto viditelný v trasování zásobníku).

## <a name="see-also"></a>Viz také:
- [IDebugObject2](../../../extensibility/debugger/reference/idebugobject2.md)