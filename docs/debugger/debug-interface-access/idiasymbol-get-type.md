---
title: IDiaSymbol::get_type | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_type method
ms.assetid: 1c6a4176-dd4e-4c22-8b8f-0e559fc078ba
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a5550ed7551e58140301f6a434d252a534b78228
ms.sourcegitcommit: 22b73c601f88c5c236fe81be7ba4f7f562406d75
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/13/2019
ms.locfileid: "56227193"
---
# <a name="idiasymbolgettype"></a>IDiaSymbol::get_type
Načte symbol, který představuje typ pro tento symbol.

## <a name="syntax"></a>Syntaxe

```C++
HRESULT get_type (
    IDiaSymbol** pRetVal
);
```

#### <a name="parameters"></a>Parametry
`pRetVal`  
[out] Vrátí [idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md) objekt, který představuje typ tento symbol.

## <a name="return-value"></a>Návratová hodnota
Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí `S_FALSE` nebo kód chyby.

> [!NOTE]
> Vrácená hodnota `S_FALSE` znamená, že vlastnost není k dispozici pro symbol.

## <a name="remarks"></a>Poznámky
Určit typ má symbol, musí volat tuto metodu a zkontrolujte výsledné [idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md) objektu. Všimněte si, že je možné pro symbol není typu mít. Například název struktury nemá žádný typ, ale může mít podřízené objekty symboly (použít [idiasymbol::findchildren –](../../debugger/debug-interface-access/idiasymbol-findchildren.md) metodu ke kontrole tyto podřízené objekty).

## <a name="example"></a>Příklad

```C++
IDiaSymbol*         pType;
CComPtr<IDiaSymbol> pBaseType;
if (SUCCEEDED(pType->get_type( &pBaseType ))) {
    BasicType btBaseType;
    if (SUCCEEDED(pBaseType->get_baseType((DWORD *)&btBaseType))) {
        // Do something with basic type.
    }
}
```

## <a name="see-also"></a>Viz také
[IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)  
[IDiaSymbol::get_baseType](../../debugger/debug-interface-access/idiasymbol-get-basetype.md)  
[IDiaSymbol::findChildren](../../debugger/debug-interface-access/idiasymbol-findchildren.md)
