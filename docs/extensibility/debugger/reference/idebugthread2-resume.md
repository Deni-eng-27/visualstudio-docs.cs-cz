---
title: IDebugThread2::Resume | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugThread2::Resume
helpviewer_keywords:
- IDebugThread2::Resume
ms.assetid: 36aad682-b0b9-40a2-b3fc-f0e61d41cdbc
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 5fc7b8f5cf5cd5360a60e8c6fbf3b6bf43415575
ms.sourcegitcommit: 6196d0b7fdcb08ba6d28a8151ad36b8d1139f2cc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/07/2019
ms.locfileid: "65225999"
---
# <a name="idebugthread2resume"></a>IDebugThread2::Resume
Pokračuje v provádění vlákna.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT Resume ( 
   DWORD *pdwSuspendCount
);
```

```csharp
int Resume ( 
   out uint pdwSuspendCount
);
```

## <a name="parameters"></a>Parametry
 `pdwSuspendCount`\

 [out] Vrátí počet pozastavení po operaci obnovení.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Každé volání této metody sníží počet potlačení dokud nedosáhne 0 na dobu, ve skutečnosti pokračování provádění. Zobrazí se tento počet pozastavení v **vlákna** okno ladění.

 Pro každé volání této metody musí být předchozí volání [pozastavit](../../../extensibility/debugger/reference/idebugthread2-suspend.md) metody. Počet potlačení Určuje, kolikrát `IDebugThread2::Suspend` dosud byla volána metoda.

## <a name="see-also"></a>Viz také:
- [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)
- [Suspend](../../../extensibility/debugger/reference/idebugthread2-suspend.md)