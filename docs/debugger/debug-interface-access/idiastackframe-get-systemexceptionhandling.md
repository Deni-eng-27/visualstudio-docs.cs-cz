---
title: IDiaStackFrame::get_systemExceptionHandling | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackFrame::get_systemExceptionHandling
ms.assetid: c76cf265-dea0-4159-883f-32b50bbef044
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 282d3ddec6e1a4de7fde3c48c5f48cf42e523747
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55026512"
---
# <a name="idiastackframegetsystemexceptionhandling"></a>IDiaStackFrame::get_systemExceptionHandling
Získá příznak, který určuje, zda systém zpracování výjimek je v platnosti.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT get_systemExceptionHandling (   
   BOOL* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pRetVal`  
 [out] Vrátí `TRUE` zpracování výjimek systému v případě platí pro tento rámec; v opačném případě vrátí `FALSE`.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`. Vrátí `S_FALSE` Pokud vlastnost není podporována. V opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Zpracování výjimek systému se také nazývá strukturované zpracování výjimek. Toto není totéž jako zpracování výjimek jazyka C++.  
  
 Chcete-li zjistit, zda zpracování výjimek jazyka C++ je v platnosti, zavolejte [idiastackframe::get_cplusplusexceptionhandling –](../../debugger/debug-interface-access/idiastackframe-get-cplusplusexceptionhandling.md) metody.  
  
## <a name="see-also"></a>Viz také  
 [IDiaStackFrame](../../debugger/debug-interface-access/idiastackframe.md)   
 [IDiaStackFrame::get_cplusplusExceptionHandling](../../debugger/debug-interface-access/idiastackframe-get-cplusplusexceptionhandling.md)