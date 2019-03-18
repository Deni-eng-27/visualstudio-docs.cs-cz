---
title: Debug_text – konstanty | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 5dde10c3-7040-46b1-a328-959c6ce5cd9f
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2342555c4ee92b403aa01cc0ca15bb805f2b002e
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58152795"
---
# <a name="debugtext-constants"></a>DEBUG_TEXT – konstanty
Využitých [IDebugExpressionContext::ParseLanguageText](../../winscript/reference/idebugexpressioncontext-parselanguagetext.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
typedef DWORD DEBUG_TEXT;  
```  
  
## <a name="constants"></a>Konstanty  
  
|Konstanta|Hodnota|Popis|  
|--------------|-----------|-----------------|  
|DWORD DEBUG_TEXT_ISEXPRESSION|0x00000001|Označuje, že text je výraz na rozdíl od příkazu. Tento příznak může mít vliv na způsob, ve kterém se analyzovat text v některých jazycích.|  
|DEBUG_TEXT_RETURNVALUE|0x00000002|Pokud vrácená hodnota je k dispozici, použije se volající.|  
|DEBUG_TEXT_NOSIDEEFFECTS|0x00000004|Nepovolit vedlejší účinky. Pokud je tento příznak nastaven, vyhodnocování výrazu by měl změnit bez běhový stav.|  
|DEBUG_TEXT_ALLOWBREAKPOINTS|0x00000008|Povolit zarážky během vyhodnocení textu. Pokud není tento příznak nastaven, bude během vyhodnocení textu ignorovat zarážky.|  
|DEBUG_TEXT_ALLOWERRORREPORT|0x00000010|Povolit zprávy o chybách během vyhodnocení textu. Pokud tento příznak není nastavena, pak chyby, nebudou ohlášena k hostiteli během hodnocení.|  
|DEBUG_TEXT_EVALUATETOCODECONTEXT|0x00000020|Označuje, že výraz má být vyhodnocen jako kontext kódu, spíše než spuštění samotného výrazu.|  
  
## <a name="see-also"></a>Viz také  
 [Konstanty, výčty a struktury ladicího programu aktivních skriptů](../../winscript/reference/active-script-debugger-constants-enumerations-and-structures.md)