---
title: 'IDiaSymbol:: get_isSdl | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- C++
ms.assetid: 6aa0e116-da75-4643-a4d7-d8e142231e21
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: abca9e52087a8cebd44ee21f9791a2ce290731d0
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "85463202"
---
# <a name="idiasymbolget_issdl"></a>IDiaSymbol::get_isSdl
Určuje, jestli je modul kompilovaný pomocí možnosti/SDL.

## <a name="syntax"></a>Syntaxe

```C++
HRESULT get_isSdl(
   BOOL *pRetVal);
```

#### <a name="parameters"></a>Parametry
 `pRetVal`

mimo Ukazatel na `BOOL` , který určuje, zda je modul zkompilován s možností/SDL.

## <a name="return-value"></a>Návratová hodnota
 V případě úspěchu vrátí, `S_OK` jinak vrátí `S_FALSE` nebo kód chyby.

## <a name="see-also"></a>Viz také
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)