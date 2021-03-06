---
title: Vrátit se zpět k funkci, která se nazývá MFC, pokud je zastavená | Microsoft Docs
ms.custom: seodec18
ms.date: 11/04/2016
ms.topic: how-to
f1_keywords:
- vs.debug.mfc
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- functions [C++], debugging
- function calls, returning to calling function
- debugging [MFC], returning to calling function
- debugging [MFC], functions
- Break command
- programs, halting
- functions [debugger]
ms.assetid: d254a5a9-afbd-4923-9d7a-7422d824cabf
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8b05e703958fe7a1c630b542522f1f33b0fe5981
ms.sourcegitcommit: ed4372bb6f4ae64f1fd712b2b253bf91d9ff96bf
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/09/2020
ms.locfileid: "89600282"
---
# <a name="how-to-get-back-to-the-function-that-called-mfc-if-halted"></a>Postupy: Přechod zpět na funkci, která volala MFC při zastavení.

> [!NOTE]
> Dialogová okna a příkazy nabídek, které vidíte, se mohou lišit od těch popsaných v nápovědě v závislosti na aktivních nastaveních nebo edici. Chcete-li změnit nastavení, v nabídce **nástroje** klikněte na položku **Nastavení importu a exportu** . Další informace najdete v tématu [resetování nastavení](../ide/environment-settings.md#reset-settings).

Pokud jste v nabídce **ladit** použili příkaz **Break** k zastavení programu a skončí v knihovně MFC a opravdu jste si jisti, že se jedná o váš kód, můžete použít okno zásobník volání a přejít zpět na svou funkci. Další informace naleznete v tématu [Postupy: použití okna zásobník volání](../debugger/how-to-use-the-call-stack-window.md).

Někdy může být váš kód v pumpě zpráv přerušen. V takovém případě není v zásobníku volání žádný uživatelský kód. Chcete-li se tomuto problému vyhnout, můžete místo příkazu **Break** použít zarážky (případně podmínky a počty přístupů). Další informace naleznete v tématu [zarážky a trasováním](/previous-versions/ktf38f66(v=vs.100)).

## <a name="navigate-to-the-function-from-which-mfc-was-called"></a>Přejděte na funkci, ze které byla volána knihovna MFC.

- Použijte okno **zásobník volání** .

## <a name="see-also"></a>Viz také

- [Nejčastější dotazy k ladění nativního kódu](../debugger/debugging-native-code-faqs.md)
- [Ladění nativního kódu](../debugger/debugging-native-code.md)