---
title: IDebugProcess2::GetPort | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProcess2::GetPort
helpviewer_keywords:
- IDebugProcess2::GetPort
ms.assetid: e39b6e5a-64eb-48cf-a53d-da4fdb968e2d
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 753a384d4873aa6b78b06853213c57a1d540a5e3
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62917828"
---
# <a name="idebugprocess2getport"></a>IDebugProcess2::GetPort
Získá port, který je proces spuštěn na.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetPort( 
   IDebugPort2** ppPort
);
```

```csharp
int GetPort( 
   out IDebugPort2 ppPort
);
```

#### <a name="parameters"></a>Parametry
 `ppPort`

 [out] Vrátí [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md) objekt, který reprezentuje port, na kterém byl proces spuštěn.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="see-also"></a>Viz také
- [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)
- [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)