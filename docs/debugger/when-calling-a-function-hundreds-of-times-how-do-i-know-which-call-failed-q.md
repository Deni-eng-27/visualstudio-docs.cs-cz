---
title: Najít, které volání se nezdařilo při volání funkce mnohokrát | Microsoft Docs
ms.custom: seodec18
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.debug.functions
dev_langs:
- CSharp
- VB
- FSharp
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
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4d054c60c45980b3d08b09987229febb99593090
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/22/2019
ms.locfileid: "72728052"
---
# <a name="when-calling-a-function-hundreds-of-times-how-do-i-know-which-call-failed"></a>Jak při opakovaném volání funkce zjistím, jaké volání bylo neúspěšné?
## <a name="problem-description"></a>Popis problému
 V programu dojde k chybě při volání určité funkce `CnvtV`. Program pravděpodobně tuto funkci zavolá několikrát, než se podařilo. Pokud nastavili zarážku umístění na `CnvtV`, program se zastaví při každém volání této funkce a nemůžu to nechci. Nevím, jaké podmínky způsobují selhání volání, takže nejde nastavit podmíněný zarážku. Co mám udělat?

## <a name="solution"></a>Řešení
 Můžete nastavit zarážku pro funkci s polem **počet** průchodů na hodnotu, aby bylo tak vysoké, že nikdy nebude dosaženo. Vzhledem k tomu, že se domníváte, že se funkce `CnvtV` nazývá více než sto, můžete nastavit **Počet volání** na 1000 nebo více. Pak spusťte program a počkejte na selhání volání. Pokud dojde k chybě, otevřete okno zarážky a Prohlédněte si seznam zarážek. Objeví se zarážka, kterou nastavíte na `CnvtV`, za nímž následuje počet volání a počet zbývajících iterací:

```cpp
CnvtV(int) (no condition) when hit count is equal to 1000 (currently 101)
```

 Nyní víte, že ve volání 101st se funkce nezdařila. Pokud resetujete zarážku s počtem volání 101 a znovu spustíte program, program se zastaví voláním `CnvtV`, které způsobily selhání.

## <a name="see-also"></a>Viz také:
- [Nejčastější dotazy k ladění nativního kódu](../debugger/debugging-native-code-faqs.md)
- [Nastavení zarážek](https://msdn.microsoft.com/library/fe4eedc1-71aa-4928-962f-0912c334d583)
- [Ladění nativního kódu](../debugger/debugging-native-code.md)
