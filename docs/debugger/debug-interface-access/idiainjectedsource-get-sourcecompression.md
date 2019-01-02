---
title: Idiainjectedsource::get_sourcecompression – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaInjectedSource::get_sourceCompression method
ms.assetid: 854b142f-23a9-466c-bf7f-98e581d5abcd
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 86679c1e97ab50f55e8f887d582e8d8b46a35ae7
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53912646"
---
# <a name="idiainjectedsourcegetsourcecompression"></a>IDiaInjectedSource::get_sourceCompression
Načte ukazatel zdroj komprese používá.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT get_sourceCompression (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pRetVal`  
 [out] Vrátí ukazatel zdroj komprese používá. Hodnota nula označuje, že se použil bez komprese zdroje.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`. Vrátí `S_FALSE` -li tato vlastnost není podporována. V opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Hodnota vrácená touto metodou je specifické pro kompilátor používají. Kompilátor může například používat kódování s délkou spustit nebo Huffmanova – vizuální styl kompresi.  
  
## <a name="see-also"></a>Viz také  
 [IDiaInjectedSource](../../debugger/debug-interface-access/idiainjectedsource.md)