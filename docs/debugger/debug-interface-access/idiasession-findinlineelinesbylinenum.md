---
title: IDiaSession::findInlineeLinesByLinenum | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: cf32ae7c-a0c8-4800-bc8f-d64fdd15fb06
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c18b2919605e3b2de6f59303c304ffb3d8f05198
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idiasessionfindinlineelinesbylinenum"></a>IDiaSession::findInlineeLinesByLinenum
Načte výčet, který umožňuje klientům k iteraci v rámci informace o všech funkcí, které jsou vložená, přímo ani nepřímo, počet zadaný zdrojový soubor a řádku číslo řádku.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT findInlineeLinesByVA (   
   IDiaSymbol*           compiland,  
   IDiaSourceFile*       file,  
   DWORD                 linenum,  
   DWORD                 column,  
   IDiaEnumLineNumbers** ppResult  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `compiland`  
 [v] [Idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md) objekt, který reprezentuje kompilace, ve kterém se má hledat čísla řádků. Tento parametr nemůže být `NULL`.  
  
 `file`  
 [v] [Idiasourcefile –](../../debugger/debug-interface-access/idiasourcefile.md) objekt, který reprezentuje zdrojový soubor, ve kterém se bude vyhledávat. Tento parametr nemůže být `NULL`.  
  
 `linenum`  
 [v] Označuje číslo, na základě jeden řádek.  
  
> [!NOTE]
>  Nelze určit všechny řádky pomocí nula (použít [idiasession::findlines –](../../debugger/debug-interface-access/idiasession-findlines.md) metody k vyhledání všechny řádky).  
  
 `column`  
 [v] Určuje počet sloupců. Pomocí nula můžete určit všechny sloupce. Sloupec je posun bajtů na čáru.  
  
 `ppResult`  
 [out] Vrátí [idiaenumlinenumbers –](../../debugger/debug-interface-access/idiaenumlinenumbers.md) objekt, který obsahuje seznam čísla řádků, které byly načteny.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [Idiasession –](../../debugger/debug-interface-access/idiasession.md)   
 [Idiasourcefile –](../../debugger/debug-interface-access/idiasourcefile.md)   
 [Idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md)   
 [SymTagEnum – výčet](../../debugger/debug-interface-access/symtagenum.md)   
 [Idiaenumlinenumbers –](../../debugger/debug-interface-access/idiaenumlinenumbers.md)