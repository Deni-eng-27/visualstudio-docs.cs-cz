---
title: IEnumDebugThreads2::GetCount | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumDebugThreads2::GetCount
helpviewer_keywords:
- IEnumDebugThreads2::GetCount
ms.assetid: 81b7f139-d24e-4040-9adc-d664d77563ba
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: ef11fcb85e061d1ecb433a0b164e2252ee5d4bd1
ms.sourcegitcommit: 50f0c3f2763a05de8482b3579026d9c76c0e226c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/09/2019
ms.locfileid: "65461159"
---
# <a name="ienumdebugthreads2getcount"></a>IEnumDebugThreads2::GetCount
Vrátí počet prvků ve výčtu.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetCount(
   ULONG* pcelt
);
```

```csharp
int GetCount(
   out uint pcelt
);
```

## <a name="parameters"></a>Parametry
 `pcelt`\

 [out] Vrátí počet prvků ve výčtu.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Tato metoda není součástí obvyklé výčet rozhraní modelu COM, který určuje pouze `Next`, `Clone`, `Skip`, a `Reset` potřeba je implementovat metody.

## <a name="see-also"></a>Viz také:
- [IEnumDebugThreads2](../../../extensibility/debugger/reference/ienumdebugthreads2.md)