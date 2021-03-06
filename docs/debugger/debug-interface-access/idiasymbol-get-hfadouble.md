---
title: 'IDiaSymbol:: get_hfaDouble | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_hfaDouble method
ms.assetid: efc247b9-c16e-4fa3-89b0-901caf7b74c3
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f294f2b64676f746cd9d155fe8c3580edc5f9821
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "85463622"
---
# <a name="idiasymbolget_hfadouble"></a>IDiaSymbol::get_hfaDouble
Načte příznak, který určuje, zda uživatelem definovaný typ (UDT) obsahuje homogenní data agregace s plovoucí desetinnou čárkou (HFA) typu Double.

## <a name="syntax"></a>Syntaxe

```C++
HRESULT get_hfaDouble( 
   BOOL* pRetVal
);
```

#### <a name="parameters"></a>Parametry
 `pRetVal`

mimo Vrátí, `TRUE` zda parametr UDT obsahuje data HFA typu Double; v opačném případě vrátí `FALSE` .

## <a name="return-value"></a>Návratová hodnota
 V případě úspěchu vrátí, `S_OK` jinak vrátí `S_FALSE` nebo kód chyby.

> [!NOTE]
> Návratová hodnota `S_FALSE` znamená, že vlastnost není k dispozici pro symbol.

## <a name="remarks"></a>Poznámky

## <a name="requirements"></a>Požadavky
 Záhlaví: Dia2. h

 Knihovna: diaguids. lib

 KNIHOVNA DLL: msdia100.dll

## <a name="see-also"></a>Viz také
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
- [IDiaSymbol::get_udtKind](../../debugger/debug-interface-access/idiasymbol-get-udtkind.md)