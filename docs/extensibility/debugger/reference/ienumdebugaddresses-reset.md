---
title: IEnumDebugAddresses::Reset | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumDebugAddresses::Reset
helpviewer_keywords:
- IEnumDebugAddresses::Reset method
ms.assetid: 3a9d7f20-5bc6-4e13-8e91-5af4092e092f
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 28819350dd0fe0c4cfb6fdc27fcd00aeb9456aea
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62867804"
---
# <a name="ienumdebugaddressesreset"></a>IEnumDebugAddresses::Reset
Tato metoda resetuje na první prvek výčtu.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT Reset(void);
```

```csharp
int Reset();
```

#### <a name="parameters"></a>Parametry
 Žádné

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Až tato metoda je volána, další volání [Další](../../../extensibility/debugger/reference/ienumdebugaddresses-next.md) vrátí první prvek výčtu.

## <a name="see-also"></a>Viz také
- [IEnumDebugAddresses](../../../extensibility/debugger/reference/ienumdebugaddresses.md)
- [Next](../../../extensibility/debugger/reference/ienumdebugaddresses-next.md)