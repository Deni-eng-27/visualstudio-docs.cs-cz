---
title: 'IDiaAddressMap:: set_imageHeaders | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaAddressMap::set_imageHeaders method
ms.assetid: a46b9d0e-43e6-433f-b2c7-aa203981e4e4
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8ded09d64a071c12e14de1597c21aad3872cacf4
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "85468544"
---
# <a name="idiaaddressmapset_imageheaders"></a>IDiaAddressMap::set_imageHeaders
Nastaví záhlaví obrázků pro povolení relativního překladu virtuálních adres.

## <a name="syntax"></a>Syntaxe

```C++
HRESULT set_imageHeaders ( 
   DWORD cbData,
   BYTE  data[],
   BOOL  originalHeaders
);
```

#### <a name="parameters"></a>Parametry
 cbData

pro Počet bajtů dat záhlaví. Musí se jednat o `n*sizeof(IMAGE_SECTION_HEADER)` `n` počet hlaviček oddílu ve spustitelném souboru.

 data []

pro Pole struktur,  `IMAGE_SECTION_HEADER` které se mají použít jako záhlaví obrázků.

 originalHeaders

pro Nastavte na `FALSE` , pokud jsou záhlaví imagí z nového obrázku, `TRUE` Pokud odrážejí původní image před upgradem. Obvykle by to bylo nastaveno `TRUE` pouze v kombinaci s voláním metody [IDiaAddressMap:: set_addressMap](../../debugger/debug-interface-access/idiaaddressmap-set-addressmap.md) .

## <a name="return-value"></a>Návratová hodnota
 V případě úspěchu vrátí. `S_OK` jinak vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 `IMAGE_SECTION_HEADER`Struktura je deklarována v souboru Winnt. h a představuje formát záhlaví oddílu image spustitelného souboru.

 Relativní výpočty virtuálních adres závisí na `IMAGE_SECTION_HEADER` hodnotách. DIA je obvykle načítá ze souboru databáze programu (PDB). Pokud tyto hodnoty chybí, DIA není schopen vypočítat relativní virtuální adresy a metoda [IDiaAddressMap:: get_relativeVirtualAddressEnabled](../../debugger/debug-interface-access/idiaaddressmap-get-relativevirtualaddressenabled.md) vrátí `FALSE` . Klient pak musí zavolat metodu [IDiaAddressMap::p ut_relativeVirtualAddressEnabled](../../debugger/debug-interface-access/idiaaddressmap-put-relativevirtualaddressenabled.md) a povolit tak relativní výpočty virtuálních adres po zadání chybějících záhlaví obrázků z obrázku samotného.

## <a name="see-also"></a>Viz také
- [IDiaAddressMap](../../debugger/debug-interface-access/idiaaddressmap.md)
- [IDiaAddressMap::set_addressMap](../../debugger/debug-interface-access/idiaaddressmap-set-addressmap.md)
- [IDiaAddressMap::get_relativeVirtualAddressEnabled](../../debugger/debug-interface-access/idiaaddressmap-get-relativevirtualaddressenabled.md)
- [IDiaAddressMap::put_relativeVirtualAddressEnabled](../../debugger/debug-interface-access/idiaaddressmap-put-relativevirtualaddressenabled.md)