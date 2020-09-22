---
title: Hledání vlákna v zobrazení vláken | Microsoft Docs
ms.date: 11/04/2016
ms.topic: how-to
helpviewer_keywords:
- threads, searching
ms.assetid: 5609a9b3-c279-4426-9e2e-dd87896a6d6f
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 99a2b4fe491939b6cf4224c211dcd03ec609be27
ms.sourcegitcommit: 062615c058d2ff44751e8d0c704ccfa3c5543469
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/22/2020
ms.locfileid: "90851980"
---
# <a name="how-to-search-for-a-thread-in-threads-view"></a>Postupy: Hledání vlákna v zobrazení vláken
Konkrétní vlákno můžete vyhledat v zobrazení vlákna pomocí jeho ID vlákna nebo řetězce modulu jako kritéria vyhledávání. Můžete také zadat počáteční směr hledání. Pole v dialogovém okně zobrazí atributy vybraného vlákna ve stromu vláken.

### <a name="to-search-for-a-thread-in-threads-view"></a>Hledání vlákna v zobrazení vláken

1. Uspořádejte okna tak, aby se zobrazilo okno pro zobrazení Spy + + a aktivní [vlákna](../debugger/threads-view.md) .

2. V nabídce **Hledat** vyberte možnost **Najít vlákno**.

    Otevře se [dialogové okno hledání vláken](../debugger/thread-search-dialog-box.md) .

3. Jako kritéria hledání zadejte ID vlákna nebo řetězec modulu.

4. Vymažte všechna pole, pro která nechcete zadávat hodnoty.

   > [!TIP]
   > Chcete-li najít všechna vlákna vlastněná modulem, zrušte zaškrtnutí políčka **vlákno** a zadejte název modulu do pole **modul** . Pak pokračujte v hledání vláken pomocí **find Next** .

5. Pro počáteční směr hledání vyberte **nahoru** nebo **dolů** .

6. Klikněte na **OK**.

   Pokud je nalezeno vyhovující vlákno, je zvýrazněno v okně zobrazení vláken.