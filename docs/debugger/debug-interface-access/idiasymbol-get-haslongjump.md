---
title: Idiasymbol::get_haslongjump – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_hasLongJump method
ms.assetid: 14484cb1-43b0-47a1-a9a8-081b55566886
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c3e942128cdf05f19ecf618cc78dcc1d401ea6ac
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56603752"
---
# <a name="idiasymbolgethaslongjump"></a>IDiaSymbol::get_hasLongJump
Získá příznak, který určuje, zda obsahuje funkci k využívání [longjmp](/cpp/c-runtime-library/reference/longjmp) příkazu (spárované s [setjmp](/cpp/c-runtime-library/reference/setjmp) příkazu, vytvářejí C-style způsob zpracování výjimek).

## <a name="syntax"></a>Syntaxe

```C++
HRESULT get_hasLongJump
   BOOL *pFlag
);
```

#### <a name="parameters"></a>Parametry
 `pFlag`

[out] Vrátí `TRUE` pokud obsahuje funkce `longjmp` příkazu; v opačném případě vrátí `FALSE`.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí `S_FALSE` nebo kód chyby.

> [!NOTE]
>  Vrácená hodnota `S_FALSE` znamená, že vlastnost není k dispozici pro symbol.

## <a name="requirements"></a>Požadavky

|Požadavek|Popis|
|-----------------|-----------------|
|Záhlaví:|dia2.h|
|Verze:|Ve verzi 8.0 DIA SDK|

## <a name="see-also"></a>Viz také
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
- [IDiaSymbol::get_hasSetJump](../../debugger/debug-interface-access/idiasymbol-get-hassetjump.md)
- [longjmp](/cpp/c-runtime-library/reference/longjmp)
- [setjmp](/cpp/c-runtime-library/reference/setjmp)