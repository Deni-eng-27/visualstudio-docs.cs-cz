---
title: IDebugProperty2::SetValueAsReference | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProperty2::SetValueAsReference
helpviewer_keywords:
- IDebugProperty2::SetValueAsReference method
ms.assetid: 341b1b89-4ab8-4e1c-abe2-fb955df5c6b0
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: ec4ee2e7ca497a6bd3429447a1d66d6b216259cf
ms.sourcegitcommit: 50f0c3f2763a05de8482b3579026d9c76c0e226c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/09/2019
ms.locfileid: "65457773"
---
# <a name="idebugproperty2setvalueasreference"></a>IDebugProperty2::SetValueAsReference
Nastaví hodnotu této vlastnosti na hodnotu daného odkazu.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT SetValueAsReference(
   IDebugReference2** rgpArgs,
   DWORD              dwArgCount,
   IDebugReference2*  pValue,
   DWORD              dwTimeout
);
```

```csharp
int SetValueAsReference(
   IDebugReference2[] rgpArgs,
   uint               dwArgCount,
   IDebugReference2   pValue,
   uint               dwTimeout
);
```

## <a name="parameters"></a>Parametry
 `rgpArgs`\

 [in] Pole argumenty pro tento zdroj vlastnosti spravovaného kódu. Pokud metoda setter vlastnosti nepřebírá argumenty nebo pokud tato [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) objekt neodkazuje na taková vlastnost setter, `rgpArgs` by měl mít hodnotu null. Tento parametr je obvykle hodnotu null.

 `dwArgCount`\

 [in] Počet argumentů `rgpArgs` pole.

 `pValue`\

 [in] Odkazem v podobě [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md) objektu na hodnotu, která slouží k nastavení této vlastnosti.

 `dwTimeout`\

 [in] Jak dlouho se má provést při nastavení hodnotu v milisekundách. Obvyklé hodnoty `INFINITE`. To má vliv na dobu, která může mít všechny možné hodnocení.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; jinak vrátí chybu kódu, obvykle jednu z následujících akcí:

|Chyba|Popis|
|-----------|-----------------|
|`E_SETVALUEASREFERENCE_NOTSUPPORTED`|Nastavením této hodnoty z odkazu není podporován.|
|`E_SETVALUE_VALUE_CANNOT_BE_SET`|Hodnotu nelze nastavit, protože tato vlastnost odkazuje na metodu.|
|`E_SETVALUE_VALUE_IS_READONLY`|Hodnota je jen pro čtení a nelze nastavit.|
|`E_NOTIMPL`|Metoda není implementována.|

## <a name="see-also"></a>Viz také:
- [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)
- [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)