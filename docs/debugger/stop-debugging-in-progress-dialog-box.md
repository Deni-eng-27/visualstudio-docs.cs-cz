---
title: "Zastavte ladění v dialogové okno průběhu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug.stopnow
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
- SQL
helpviewer_keywords: Stop Debugging in Progress dialog box
ms.assetid: ed7ef49d-e25f-4a4d-9396-9bc7b4143117
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5c056882d1a5c7eca4a7e09d040753d139c89b5e
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="stop-debugging-in-progress-dialog-box"></a>Dialogové okno Ukončit probíhající ladění
Toto dialogové okno se zobrazí, když se při pokusu o zastavení ladicí relace je v ladicím programu, ale ukončení relace se blíží chvíli trvat. Zastavení ladicí relace je obvykle velmi rychlé a tohoto dialogového okna se nezobrazí. V některých případech ale trvá odpojení od všech procesů laděné dobu. Pokud zastavování relace trvá víc než několik sekund (nebo pokud dojde k chybě odpojení), zobrazí se toto dialogové okno. Pokud k tomu dochází často, může být kvůli internímu problému a můžete chtít obraťte se na oddělení technické podpory.  
  
 Můžete počkat procesy odpojit a dialogové okno k zmizí nebo použít **zastavit teď** tlačítko chcete vynutit okamžitou ukončení.  
  
 **Zastavit nyní**  
 Kliknutím na toto tlačítko Ukončit relaci ladění okamžitě. Pomocí **zastavit teď** místo odpojování procesy laděné bude ukončen. Pokud ladíte systémových procesů, ukončení tyto procesy s **zastavit teď** může mít neočekávané a nežádoucí účinky.  
  
## <a name="see-also"></a>Viz také  
 [Zabezpečení ladicího programu](../debugger/debugger-security.md)   
 [Odpojování programy](http://msdn.microsoft.com/en-us/f2c756c2-8079-474b-94c2-01c19a141a01)