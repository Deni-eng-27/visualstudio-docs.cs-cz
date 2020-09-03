---
title: Jak mohu ladit porušení přístupu, když program spouštím mimo ladicí program? | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.access
dev_langs:
- FSharp
- VB
- CSharp
- C++
- C++
helpviewer_keywords:
- access violation debugging
- debugging [Visual Studio], access violations
ms.assetid: 780a298a-132e-4245-8370-8c82ca27c6c1
caps.latest.revision: 22
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: ce5b21f92eecf2e8929c142bc1ee32e20d386335
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "74299254"
---
# <a name="how-can-i-debug-access-violations-when-running-my-program-outside-the-debugger"></a>Jak mohu ladit porušení přístupu, když program spouštím mimo ladicí program?
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Popis problému  
 Můj program funguje v prostředí sady Visual Studio správně, ale když ho spouštíte samostatně s operačním systémem Windows, dojde k narušení přístupu. Jak mohu tento problém ladit?  
  
## <a name="solution"></a>Řešení  
 Nastavte možnost [ladění za běhu](../debugger/just-in-time-debugging-in-visual-studio.md) a spusťte program samostatně, dokud nedojde k narušení přístupu. Pak můžete v dialogovém okně **porušení přístupu** kliknutím na tlačítko **Storno** spustit ladicí program.  
  
 Podívejte se také na článek znalostní báze Q133174, jak najít, kde dochází k chybě obecné ochrany (GP). " Články znalostní báze najdete na disku CD knihovny MSDN nebo hledáním [http://support.microsoft.com/](https://support.microsoft.com/) .  
  
## <a name="see-also"></a>Viz také  
 [Nejčastější dotazy k ladění nativního kódu](../debugger/debugging-native-code-faqs.md)   
 [Ladění nativního kódu](../debugger/debugging-native-code.md)
