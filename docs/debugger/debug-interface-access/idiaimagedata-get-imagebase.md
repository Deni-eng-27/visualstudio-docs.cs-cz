---
title: 'IDiaImageData:: get_imageBase | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaImageData::get_imageBase method
ms.assetid: 4ba3d9e4-b205-4ee6-a41d-6996972f1f85
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 00461f73059198f5e9028658100c9ccf400be607
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "85467174"
---
# <a name="idiaimagedataget_imagebase"></a>IDiaImageData::get_imageBase
Načte umístění paměti, kde má být obrázek založen.

## <a name="syntax"></a>Syntaxe

```C++
HRESULT get_imageBase ( 
   ULONGLONG* pRetVal
);
```

#### <a name="parameters"></a>Parametry
 `pRetVal`

mimo Vrátí navrhovanou základní hodnotu obrázku.

## <a name="return-value"></a>Návratová hodnota
 V případě úspěchu vrátí. `S_OK` jinak vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Vzhledem k tomu, že jsou v konfliktu s obrázkem, může se při načtení image automaticky znovu zakládat do nevyužitého místa v paměti. Tato metoda vrátí základní pomocný parametr (navrhované umístění v paměti), který byl uložen v modulu v době kompilace.

## <a name="see-also"></a>Viz také
- [IDiaImageData](../../debugger/debug-interface-access/idiaimagedata.md)