---
title: 'Postupy: Hledání procesu v zobrazení procesů | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- Processes view
- processes, searching for
ms.assetid: 7cb97b37-4a95-4f1b-9eee-4910aa9c115b
caps.latest.revision: 7
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: e39168e36e9540ec8c5e23a9030d996b81c4097c
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63431733"
---
# <a name="how-to-search-for-a-process-in-processes-view"></a>Postupy: Hledání procesu v zobrazení procesů
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Můžete vyhledat konkrétního procesu v zobrazení procesů pomocí jeho ID nebo modul řetězec proces jako kritéria hledání. Můžete také zadat počáteční směr hledání. Pole v dialogovém okně se zobrazí atributy vybraný proces strom procesu.  
  
### <a name="to-search-for-a-process-in-processes-view"></a>Hledání procesu v zobrazení procesů  
  
1. Uspořádat okna tak tohoto nástroje Spy ++ a aktivní [zobrazení procesy](../debugger/processes-view.md) okna jsou viditelné.  
  
2. Z **hledání** nabídce zvolte **najít proces**  
  
    [Dialogové okno hledání procesů](../debugger/process-search-dialog-box.md) otevře.  
  
3. Zadejte ID procesu nebo řetězce modulu, jako kritéria hledání.  
  
4. Zrušte zaškrtnutí všech polí, u kterých nechcete k určení hodnot.  
  
   > [!TIP]
   > Pokud chcete najít všechny procesy vlastní modul, zrušte **procesu** pole a zadejte název modulu v **modulu** pole. Pak pomocí **najít další** chcete pokračovat ve vyhledávání pro procesy.  
  
5. Zvolte **nahoru** nebo **dolů** pro počáteční směr hledání.  
  
6. Klikněte na **OK**.  
  
   Pokud je nalezen odpovídající proces, je zvýrazněn **zobrazení procesů** okna.
