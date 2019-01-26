---
title: Ladit aplikaci, která není součástí řešení sady Visual Studio
titleSuffix: ''
ms.custom: seodec18
ms.date: 11/19/2018
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- debugging [Visual Studio], executables
- executable files, importing
- executable files, debugging outside of projects
ms.assetid: 3ea176e8-1ce5-42c4-b7a2-abe3a2765033
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 2ae2ea60a4f2427cbe1509a8fa05c787d44b19d7
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55019132"
---
# <a name="debug-an-app-that-isnt-part-of-a-visual-studio-solution-c-c-visual-basic-f"></a>Ladit aplikaci, která není součástí řešení sady Visual Studio (C++, C#, Visual Basic, F#)

Můžete chtít ladit aplikaci (*.exe* souboru), který není součástí řešení sady Visual Studio. Vy nebo někdo jiný může mít vytvořili aplikaci mimo sadu Visual Studio, nebo jste aplikaci získali z někde jinde. 

Obvyklým způsobem dovolují ladit aplikaci, která neexistuje v sadě Visual Studio je spuštění aplikace mimo sadu Visual Studio a připojte se k němu pomocí **připojit k procesu** v ladicím programu sady Visual Studio. Další informace najdete v tématu [připojení ke spuštěným procesům](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md).  
  
Připojení k aplikaci vyžaduje vyžadováno provedení ručních kroků, které pár sekund trvat. Kvůli tomuto zpoždění připojení nepomůže, ladění potíží při spuštění nebo vstupní aplikace, který nečeká na uživatele a rychle skončí. 

V těchto situacích můžete vytvořit projekt Visual Studio EXE pro aplikace, nebo ji naimportovat do existující C#, Visual Basic nebo C++ řešení. Ne všechny programovací jazyky podporují projekty EXE. 

>[!IMPORTANT]
>Funkce ladění pro aplikace, které nebylo vytvořené v sadě Visual Studio jsou omezeny, ať už jste připojení k aplikaci nebo ho přidat do řešení sady Visual Studio. 
>
>Pokud máte zdrojový kód, nejlepším řešením je import kódu do projektu sady Visual Studio. Potom spusťte sestavení pro ladění aplikace.
>
>Pokud nemáte zdrojový kód a aplikace nebude mít [informace o ladění](../debugger/how-to-set-debug-and-release-configurations.md) v kompatibilním formátu, jsou velmi málo dostupné funkce ladění. 

### <a name="to-create-a-new-exe-project-for-an-existing-app"></a>Chcete-li vytvořit nový projekt EXE pro stávající aplikace  
   
1. V sadě Visual Studio, vyberte **souboru** > **otevřít** > **projektu**.  
   
1. V **otevřít projekt** dialogu **všechny soubory projektu**, pokud ještě není vybraná, v rozevíracím seznamu vedle **název_souboru**.  
   
1. Přejděte *.exe* souboru, vyberte ho a vyberte **otevřít**.  
   
   Tento soubor objeví nové dočasné řešení sady Visual Studio.

1. Zahájit ladění aplikace výběrem příkazu ke spuštění, jako je třeba **spustit ladění**, z **ladění** nabídky.    
  
### <a name="to-import-an-app-into-an-existing-visual-studio-solution"></a>Importovat aplikace do existujícího řešení sady Visual Studio  
  
1.  V jazyce C++ C#, nebo Visual Basic řešení otevřít v sadě Visual Studio, vyberte **souboru** > **přidat** > **existující projekt**.  
  
1. V **otevřít projekt** dialogu **všechny soubory projektu**, pokud ještě není vybraná, v rozevíracím seznamu vedle **název_souboru**.  
   
1. Přejděte *.exe* souboru, vyberte ho a vyberte **otevřít**.  
   
   Soubor se zobrazí jako nový projekt v aktuálním řešení.  
   
1. Vybraný nový soubor, spustit ladění aplikace výběrem příkazu ke spuštění, jako je třeba **spustit ladění**, z **ladění** nabídky.    
  
### <a name="see-also"></a>Viz také:  
 [Nastavení ladicího programu a příprava](../debugger/debugger-settings-and-preparation.md)   
 [Zabezpečení ladicího programu](../debugger/debugger-security.md)   
 [Soubory DBG](/previous-versions/visualstudio/visual-studio-2010/da528y14(v=vs.100))