---
title: Idiaaddressmap – | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaAddressMap interface
ms.assetid: e6467529-508c-4328-85d7-89444ae4d1c1
caps.latest.revision: 13
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 012d6b1ca06b06f56239048fee712d898a79efa9
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54780105"
---
# <a name="idiaaddressmap"></a>IDiaAddressMap
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Umožňuje řídit jak DIA SDK vypočítá virtuální a relativní virtuální adresy pro ladění objektů.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDiaAddressMap : IUnknown  
```  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 V následující tabulce jsou uvedeny metody objektu `IDiaAddressMap`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IDiaAddressMap::get_addressMapEnabled](../../debugger/debug-interface-access/idiaaddressmap-get-addressmapenabled.md)|Označuje, zda mapování adres se vytvořilo pro konkrétní relace.|  
|[IDiaAddressMap::put_addressMapEnabled](../../debugger/debug-interface-access/idiaaddressmap-put-addressmapenabled.md)|Určuje, zda mapování adres má použít k překladu adres symbol.|  
|[IDiaAddressMap::get_relativeVirtualAddressEnabled](../../debugger/debug-interface-access/idiaaddressmap-get-relativevirtualaddressenabled.md)|Určuje, zda je povoleno výpočtu a používání relativních virtuálních adres.|  
|[IDiaAddressMap::put_relativeVirtualAddressEnabled](../../debugger/debug-interface-access/idiaaddressmap-put-relativevirtualaddressenabled.md)|Umožňuje klientovi k povolení nebo zakázání výpočtu relativních virtuálních adres.|  
|[IDiaAddressMap::get_imageAlign](../../debugger/debug-interface-access/idiaaddressmap-get-imagealign.md)|Načte aktuální zarovnání obrázku.|  
|[IDiaAddressMap::put_imageAlign](../../debugger/debug-interface-access/idiaaddressmap-put-imagealign.md)|Nastaví zarovnání obrázku.|  
|[IDiaAddressMap::set_imageHeaders](../../debugger/debug-interface-access/idiaaddressmap-set-imageheaders.md)|Nastaví obrázek záhlaví povolit překlad relativních virtuálních adres.|  
|[IDiaAddressMap::set_addressMap](../../debugger/debug-interface-access/idiaaddressmap-set-addressmap.md)|Poskytuje mapování adres pro podporu překlady rozvržení obrázku.|  
  
## <a name="remarks"></a>Poznámky  
 Toto rozhraní poskytuje ovládací prvek, je zapouzdřena v dvě sady dat zadáte: obrázek záhlaví a řešit mapy. Většina klientů použijte [idiadatasource::loaddataforexe –](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md) metody k vyhledání správné ladicí informace pro bitovou kopii a metodu lze obvykle zjistit všechny potřebné hlavičky a mapy vlastní data. Ale někteří klienti implementovat specializovaný zpracování a vyhledávat data. Tito klienti použití metod pro posunutí `IDiaAddressMap` rozhraní k poskytování DIA SDK ve výsledcích vyhledávání.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Toto rozhraní je k dispozici z objektu relace DIA. Volání klienta `QueryInterface` metodu na DIA relace objekt rozhraní, obvykle [idiasession –](../../debugger/debug-interface-access/idiasession.md), k načtení `IDiaAddressMap` rozhraní.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: Dia2.h  
  
 Knihovna: diaguids.lib  
  
 DLL: msdia80.dll  
  
## <a name="see-also"></a>Viz také  
 [Rozhraní (Debug Interface Access SDK)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [IDiaDataSource::loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)   
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)
