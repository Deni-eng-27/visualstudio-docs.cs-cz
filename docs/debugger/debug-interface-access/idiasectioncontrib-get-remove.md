---
title: Idiasectioncontrib::get_remove – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSectionContrib::get_remove method
ms.assetid: fd30ab7b-022b-4402-a42a-2d38e274c1b1
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 3baca305a96fbb7268058e930ae443215410b626
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54919847"
---
# <a name="idiasectioncontribgetremove"></a>IDiaSectionContrib::get_remove
Získá příznak, který určuje, zda je v části odebrat předtím, než je k součástí bitové kopie v paměti.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT get_remove (   
   BOOL* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pRetVal`  
 [out] Vrátí `TRUE` oddíl je nechcete přidat do bitové kopie v paměti; v opačném případě vrátí `FALSE`.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`. Vrátí `S_FALSE` -li tato vlastnost není podporována. V opačném případě vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IDiaSectionContrib](../../debugger/debug-interface-access/idiasectioncontrib.md)