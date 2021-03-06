---
title: Zobrazení vláken GPU v ladicím programu | Microsoft Docs
ms.date: 11/04/2016
ms.topic: how-to
f1_keywords:
- vs.debug.gputthreads
- vs.debug.gputhreads
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugger, GPU threads window
ms.assetid: c647c502-a9f0-48e0-a430-976744a5fa51
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: cbbb49a1017fb0bc65300f3c16050db4954e1103
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "85348714"
---
# <a name="how-to-use-the-gpu-threads-window-c"></a>Postupy: použití okna vláken GPU (C++)
V okně vlákna GPU můžete prozkoumat a pracovat s vlákny, které jsou spuštěny na GPU v aplikaci, kterou ladíte. Další informace o aplikacích, které běží na GPU, najdete v tématu [C++ amp Overview](/cpp/parallel/amp/cpp-amp-overview).

 Okno vlákna GPU obsahuje tabulku, ve které každý řádek představuje sadu vláken GPU, která má stejné hodnoty ve všech sloupcích. Položky, které jsou ve sloupcích, můžete řadit, přeřadit, odebírat a seskupovat. Vlákna můžete označit, odblokovat (pozastavit) a uvolnit (obnovit) z okna vlákna GPU. V okně vlákna GPU se zobrazí následující sloupce:

- Sloupec příznak, ve kterém můžete označit vlákno, kterému chcete věnovat zvláštní pozornost.

- Aktuální sloupec vlákna, ve kterém žlutá šipka indikuje aktuální vlákno.

- Sloupec **počet vláken** , který zobrazuje počet vláken ve stejném umístění.

- Sloupec **line** , který zobrazuje řádek kódu, kde se nachází každá skupina vláken.

- Sloupec **adresa** , který zobrazuje adresu instrukcí, kde se nachází každá skupina vláken. Ve výchozím nastavení je tento sloupec skrytý.

- Sloupec **umístění** , což je umístění ve zdrojovém kódu.

- Sloupec **Status (stav** ), který ukazuje, zda je vlákno aktivní, blokováno, není spuštěno nebo dokončeno.

- Sloupec **dlaždice** , který zobrazuje index dlaždice pro vlákna na řádku.

  Záhlaví tabulky zobrazuje dlaždici a zobrazované vlákno.

  [!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]

### <a name="to-display-the-gpu-threads-window"></a>Zobrazení okna vláken GPU

1. V **Průzkumník řešení**otevřete místní nabídku pro projekt a poté zvolte možnost **vlastnosti**.

2. V okně **stránky vlastností** projektu klikněte v části **Vlastnosti konfigurace**na možnost **ladění**.

3. V seznamu **Spustit ladicí program** vyberte **místní ladicí program systému Windows**. V seznamu **Typ ladicího programu** vyberte **pouze GPU**. Je nutné zvolit tento ladicí program pro přerušení u zarážek v kódu, který běží na GPU.

4. Klikněte na tlačítko **OK** .

5. Nastavte zarážku v kódu GPU.

6. Na řádku nabídek klikněte na položku **ladit**, **Spustit ladění**. Počkejte, než aplikace dorazí na zarážku.

7. Na panelu nabídek vyberte možnost **ladit**, **Windows**, **vlákna GPU**.

### <a name="to-switch-to-a-different-thread"></a>Přepnutí na jiné vlákno

- Dvakrát klikněte na sloupec. (Klávesnice: vyberte řádek a zvolte Enter.)

### <a name="to-display-a-particular-tile-and-thread"></a>Zobrazení konkrétní dlaždice a vlákna

1. V okně vlákna GPU vyberte tlačítko **Rozbalit přepínač vlákna** .

2. Do textových polí zadejte dlaždice a hodnoty vláken.

3. Klikněte na tlačítko se šipkou.

### <a name="to-display-or-hide-a-column"></a>Zobrazení nebo skrytí sloupce

- Otevřete místní nabídku okna vlákna GPU, zvolte **sloupce**a potom zvolte sloupec, který chcete zobrazit nebo skrýt.

### <a name="to-sort-by-a-column"></a>Řazení podle sloupce

- Vyberte záhlaví sloupce.

### <a name="to-group-threads"></a>Seskupení vláken

- Otevřete místní nabídku okna vlákna GPU, zvolte možnost **Seskupit podle**a potom zvolte jeden ze zobrazených názvů sloupců. Pokud chcete zrušit seskupení vláken, vyberte **none** .

### <a name="to-freeze-or-thaw-a-row-of-threads"></a>Zablokování nebo odmrazení řádku vláken

- Otevřete místní nabídku řádku a vyberte možnost **ukotvit** nebo **rozmrazit**.

### <a name="to-flag-or-unflag-a-row-of-threads"></a>Označení nebo odoznačení řádku vláken příznakem

- Vyberte sloupec příznak pro vlákno, nebo otevřete místní nabídku pro vlákno a zvolte **příznak** nebo zrušit **označení**.

### <a name="to-display-only-flagged-threads"></a>Chcete-li zobrazit pouze vlákna označená příznakem

- V okně vlákna GPU vyberte tlačítko příznak.

## <a name="see-also"></a>Viz také
- [Ladění vícevláknových aplikací](../debugger/debug-multithreaded-applications-in-visual-studio.md)
- [Postupy: použití okna paralelního sledování](../debugger/how-to-use-the-parallel-watch-window.md)
- [Návod: ladění aplikace C++ AMP](/cpp/parallel/amp/walkthrough-debugging-a-cpp-amp-application)