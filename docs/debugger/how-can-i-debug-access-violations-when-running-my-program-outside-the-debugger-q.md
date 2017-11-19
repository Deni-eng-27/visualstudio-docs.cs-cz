---
title: "Jak mohu ladit porušení přístupu, když program spouštím mimo ladicí program? | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug.access
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- access violation debugging
- debugging [Visual Studio], access violations
ms.assetid: 780a298a-132e-4245-8370-8c82ca27c6c1
caps.latest.revision: "19"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d1b8a6e019725f95788b4988fbe1ddef18cb27cc
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-can-i-debug-access-violations-when-running-my-program-outside-the-debugger"></a>Jak mohu ladit porušení přístupu, když program spouštím mimo ladicí program?
## <a name="problem-description"></a>Popis problému  
 Program lze spustit v prostředí Visual Studio dobře, ale při opakovaném spuštění samostatné s operačním systémem Windows, vyvolá porušení přístupu. Jak mohu ladit tento problém?  
  
## <a name="solution"></a>Řešení  
 Nastavte [pouze za běhu ladění](../debugger/just-in-time-debugging-in-visual-studio.md) možnost a spusťte svůj program samostatné, dokud dojde k porušení přístupu. Potom v **narušení přístupu** dialogové okno, můžete kliknout na **zrušit** spuštění ladicího programu.  
  
 Také najdete v článku znalostní báze Knowledge Base Q133174, "Postup vyhledání, kde dochází k chybu obecné ochrany (zásady skupiny)." Můžete vyhledat články znalostní báze Knowledge Base na disku CD knihovny MSDN nebo tak, že [http://support.microsoft.com/](http://support.microsoft.com/).  
  
## <a name="see-also"></a>Viz také  
 [Nativní kód nejčastější dotazy k ladění](../debugger/debugging-native-code-faqs.md)   
 [Ladění nativního kódu](../debugger/debugging-native-code.md)