---
title: IDebugField::GetExtendedInfo | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugField::GetExtendedInfo
helpviewer_keywords:
- IDebugField::GetExtendedInfo method
ms.assetid: 46c0dd4d-4fd5-4efd-a908-71e4248e8e8d
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: fc37cd9cff4956d000441a632f84a6155f9b9586
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/24/2019
ms.locfileid: "66212219"
---
# <a name="idebugfieldgetextendedinfo"></a>IDebugField::GetExtendedInfo
Tato metoda získá rozšířené informace o pole.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetExtendedInfo( 
   REFGUID guidExtendedInfo,
   BYTE**  prgBuffer,
   DWORD*  pdwLen
);
```

```csharp
int GetExtendedInfo(
   ref Guid guidExtendedInfo,
   IntPtr[] prgBuffer,
   ref uint pdwLen
);
```

## <a name="parameters"></a>Parametry
`guidExtendedInfo`\
[in] Vybere informace, které se mají vrátit. Platné hodnoty jsou:

|Value|Popis|
|-----------|-----------------|
|`guidConstantValue`|Hodnota jako sekvence bajtů.|
|`guidConstantType`|Typ jako typ podpisu.|

`prgBuffer`\
[out] Vrátí rozšířené informace.

`pdwLen`\
[out v] Vrátí velikost rozšířených informací v bajtech.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 V současné době tato metoda vrátí pouze typem nebo hodnotou konstanty. Volající musí uvolnit vrácené ve vyrovnávací paměti `prgBuffer` volala modelu COM `CoTaskMemFree` – funkce (C++) nebo <xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A> (C#).

## <a name="see-also"></a>Viz také:
- [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)