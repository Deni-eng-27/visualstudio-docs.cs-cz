---
title: IDebugEngine2::RemoveSetException | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugEngine2::RemoveSetException
helpviewer_keywords:
- IDebugEngine2::RemoveSetException
ms.assetid: bdd25097-0e9d-4218-b417-0497ea48d2e8
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 2d4e8e919f69736025eb211dfd46ee72f461839d
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56679369"
---
# <a name="idebugengine2removesetexception"></a>IDebugEngine2::RemoveSetException
Odebere Zadaná výjimka, takže už je zpracována ladicího stroje.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT RemoveSetException( 
   EXCEPTION_INFO* pException
);
```

```csharp
int RemoveSetException( 
   EXCEPTION_INFO[] pException
);
```

#### <a name="parameters"></a>Parametry
 `pException`

 [in] [EXCEPTION_INFO](../../../extensibility/debugger/reference/exception-info.md) struktura, která popisuje výjimku, která se má odebrat.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Odebrání výjimky musí dříve nastavit dřívějším volání [SetException](../../../extensibility/debugger/reference/idebugengine2-setexception.md) metody.

 Chcete-li odebrat všechny výjimky sadě najednou, zavolejte [RemoveAllSetExceptions](../../../extensibility/debugger/reference/idebugengine2-removeallsetexceptions.md) metody.

## <a name="see-also"></a>Viz také
- [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)
- [EXCEPTION_INFO](../../../extensibility/debugger/reference/exception-info.md)