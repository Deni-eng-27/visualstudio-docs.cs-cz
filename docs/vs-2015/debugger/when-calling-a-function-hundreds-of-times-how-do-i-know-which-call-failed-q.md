---
title: Jak při opakovaném volání funkce zjistím, jaké volání bylo neúspěšné? | Dokumenty Microsoft
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.functions
dev_langs:
- FSharp
- VB
- CSharp
- C++
- C++
helpviewer_keywords:
- conditional breakpoints
- errors [debugger], function calls
- breakpoints, troubleshooting
- errors [debugger], finding which function call failed
- failures
- location breakpoint call failures
- errors [Visual Studio], function calls
- hit counts
- function calls, failure
- functions [debugger]
- Skip Count
ms.assetid: 66cfac86-f5be-4d3a-9329-d44cd74bc586
caps.latest.revision: 20
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 2b3cfa5c52b8ddbe53ce127fde60a9b4edfd8ddd
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54775303"
---
# <a name="when-calling-a-function-hundreds-of-times-how-do-i-know-which-call-failed"></a>Jak při opakovaném volání funkce zjistím, jaké volání bylo neúspěšné?
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Popis problému  
 Program selže při volání na určitou funkci, `CnvtV`. Program pravděpodobně volá tuto funkci několik stovek časy předtím, než selže. Je-li nastavit zarážku umístění na `CnvtV`, program se zastaví při každém volání této funkce a která nechci. Nevím, jaké podmínky způsobit, že volání selže, takže nelze nastavit podmíněné zarážky. Co mám udělat?  
  
## <a name="solution"></a>Řešení  
 U funkce s můžete nastavit zarážku **počet volání** pole na hodnotu tak velká, že ho bude nikdy dosažen. V takovém případě vzhledem k tomu, že si myslíte, že funkce `CnvtV` nazývá několik stovek dobu, může být nastavena **počet volání** na 1000 nebo více. Potom spusťte program a počkejte, volání selže. Pokud se nezdaří, otevřete okno zarážky a podívejte se na seznamu zarážek. Se zarážka nastavila na `CnvtV` se zobrazí, za nímž následuje počet průchodů a počet zbývajících opakování:  
  
```  
CnvtV(int) (no condition) when hit count is equal to 1000 (currently 101)  
```  
  
 Teď už víte, že funkce se nezdařila při 101st volání. Pokud obnovíte tovární nastavení zarážky se počet přístupů, 101 a program spusťte znovu, program se zastaví u volání `CnvtV` , který způsobil, že k selhání.  
  
## <a name="see-also"></a>Viz také  
 [Ladění nativního kódu nejčastější dotazy](../debugger/debugging-native-code-faqs.md)   
 [Nastavení zarážek](http://msdn.microsoft.com/fe4eedc1-71aa-4928-962f-0912c334d583)   
 [Ladění nativního kódu](../debugger/debugging-native-code.md)
