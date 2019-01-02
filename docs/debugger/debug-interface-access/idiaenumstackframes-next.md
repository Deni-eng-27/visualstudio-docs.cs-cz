---
title: Idiaenumstackframes::Next – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumStackFrames::Next method
ms.assetid: 09378a21-d5e3-4213-b7e2-10f04d85295f
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 781b86d405057ddfe70bcde9199ec4094d896288
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53828196"
---
# <a name="idiaenumstackframesnext"></a>IDiaEnumStackFrames::Next
Načte zadaný počet prvků rámce zásobníku v pořadí výčtu.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT Next(   
   ULONG             celt,  
   IDiaStackFrame**  rgelt,  
   ULONG*            pceltFetched  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 celt  
 [in] Počet prvků stackframe v enumerátor, který se má načíst.  
  
 rgelt  
 [out] Pole, které je pro vyplnění s požadovaným [idiastackframe –](../../debugger/debug-interface-access/idiastackframe.md) objekty.  
  
 pceltFetched  
 [out] Vrátí počet zásobníku rámce prvků načtených enumerátor.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`. Vrátí `S_FALSE` Pokud nejsou žádné další rámce zásobníku. V opačném případě vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [Idiaenumstackframes –](../../debugger/debug-interface-access/idiaenumstackframes.md)   
 [IDiaStackFrame](../../debugger/debug-interface-access/idiastackframe.md)