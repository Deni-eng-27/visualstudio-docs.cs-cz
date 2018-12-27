---
title: Představení nástroje Spy ++ | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- Spy++
ms.assetid: 733b514b-63a9-402d-89aa-4f0416766655
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d9fceb83f915eb1a90a781d886c84fd40651cc0a
ms.sourcegitcommit: a205ff1b389fba1803acd32c54df7feb0ef7a203
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/20/2018
ms.locfileid: "53647320"
---
# <a name="introducing-spy"></a>Představení nástroje Spy++
Spy ++ umožňuje provádět následující úlohy:  
  
- Zobrazte grafické strom vztahů mezi objekty systému. Patří mezi ně [procesy](../debugger/processes-view.md), [vlákna](../debugger/threads-view.md), a [windows](../debugger/windows-view.md).  
  
- Hledání pro zadané [windows](../debugger/how-to-search-for-a-window-in-windows-view.md), [vlákna](../debugger/how-to-search-for-a-thread-in-threads-view.md), [procesy](../debugger/how-to-search-for-a-process-in-processes-view.md), nebo [zprávy](../debugger/how-to-search-for-a-message-in-messages-view.md).  
  
- Zobrazit vlastnosti vybrané [windows](../debugger/how-to-display-window-properties.md), [vlákna](../debugger/how-to-display-thread-properties.md), [procesy](../debugger/how-to-display-process-properties.md), nebo [zprávy](../debugger/how-to-display-message-properties.md).  
  
- Vyberte okno, vlákno, proces nebo zprávy přímo v zobrazení.  
  
- Použití [tažením nástroje hledání](../debugger/how-to-use-the-finder-tool.md) vyberte okno umístěním ukazatele myši.  
  
- Nastavte [zprávy možnost](../debugger/how-to-open-messages-view-from-find-window.md) s využitím komplexních zprávy protokolu výběr parametrů.  
  
  Spy ++ má panel nástrojů a hypertextové odkazy vám pomohou při práci rychleji. Poskytuje také **aktualizovat** příkaz k aktualizaci zobrazení aktivní **nástroj pro hledání oken** aby bylo sledování snazší a **písmo** dialogové okno pro přizpůsobení zobrazení systému windows. Kromě toho nástroje Spy ++ umožňuje uložení a obnovení uživatelských předvoleb.  
  
  V různých nástroje Spy ++ windows kliknete pravým tlačítkem na Zobrazit místní nabídku s často používanými příkazy. Příkazy, které jsou zobrazeny, závisí na místě, kde je ukazatel. Například pokud kliknete pravým tlačítkem na položku v zobrazení okna a je vybrané okno viditelné, pak levým na **zvýrazněte** na zástupce v nabídce způsobí, že hranice vybrané okno pro flash, takže může být umístěn snadněji.  
  
> [!NOTE]
>  Existují dva nástroje, které se podobají nástroje Spy ++: PView, která zobrazuje podrobnosti o procesech a vláknech a DDESPY. Exe souboru, který vám umožní monitorovat dynamické výměny dat (DDE) zprávy.  
  
## <a name="64-bit-operating-systems"></a>64bitová verze operačních systémů  
 Existují dvě verze nástroje Spy ++. První verze, s názvem nástroje Spy ++ (spyxx.exe) slouží k zobrazení zprávy odeslané do okna, na kterém běží v 32bitový proces. Visual Studio spustí třeba v 32bitový proces. Proto můžete nástroje Spy ++ pro zobrazení zprávy odeslané do **Průzkumníka řešení**. Jelikož výchozí konfigurace pro většinu sestavení v sadě Visual Studio je spuštění v procesu 32-bit, první verzi nástroje Spy ++, je ten, který je k dispozici na **nástroje** nabídky v sadě Visual Studio, pokud [požadované součásti nainstalované](../debugger/how-to-start-spy-increment.md). 
  
 Druhá verze, s názvem nástroje Spy ++ (64-bit) (spyxx_amd64.exe), je navržená pro zobrazení zprávy odeslané do okna, na kterém běží v 64bitové proces. Na 64bitový operační systém, například Poznámkový blok spustí v 64bitového procesu. Proto můžete nástroje Spy ++ (64-bit) k zobrazení zprávy odeslané do poznámkového bloku. Spy ++ (64-bit) se obvykle nachází v  
  
 .. \\ *Instalační složky sady visual Studio*\Common7\Tools\spyxx_amd64.exe.  
  
 Buď verzi nástroje Spy ++ lze spustit přímo z příkazového řádku.  
  
> [!NOTE]
>  I když se název souboru (64-bit) nástroje Spy ++ obsahuje "amd", běží na libovolné x64 operačního systému Windows.  
  
## <a name="see-also"></a>Viz také 
 [Postupy: Spuštění nástroje Spy ++](../debugger/how-to-start-spy-increment.md)   
 [Použití nástroje Spy ++](../debugger/using-spy-increment.md)   
 [Zobrazení nástroje Spy ++](../debugger/spy-increment-views.md)   
 [Referenční dokumentace nástroje Spy++](../debugger/spy-increment-reference.md)