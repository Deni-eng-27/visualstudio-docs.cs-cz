---
title: IDebugPortSupplier2::GetPort | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugPortSupplier2::GetPort
helpviewer_keywords:
- IDebugPortSupplier2::GetPort
ms.assetid: d55d5055-7386-4037-bf22-4c3e434a99ca
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 65b2d8264ef75c46de32ee65d994794d526c7ddb
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56693058"
---
# <a name="idebugportsupplier2getport"></a>IDebugPortSupplier2::GetPort
Získá od jiného dodavatele portu port.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetPort( 
   REFGUID       guidPort,
   IDebugPort2** ppPort
);
```

```csharp
int GetPort( 
   ref Guid        guidPort,
   out IDebugPort2 ppPort
);
```

#### <a name="parameters"></a>Parametry
 `guidPort`

 [in] Globálně jedinečný identifikátor (GUID) portu.

 `ppPort`

 [out] Vrátí [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md) objekt, který reprezentuje port.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby. Vrátí `E_PORTSUPPLIER_NO_PORT` Pokud neexistuje žádný port s daným identifikátorem.

## <a name="see-also"></a>Viz také
- [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md)
- [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)