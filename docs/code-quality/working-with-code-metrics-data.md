---
title: Okno metriky kódu
ms.date: 12/12/2017
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- vs.codemetrics.output
helpviewer_keywords:
- code metrics results
- code metrics results window
- results window, code metrics
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ea95a5c64a4f3bbe6332542aee84d0ec0b12ec3e
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55036196"
---
# <a name="use-the-code-metrics-results-window"></a>Použijte okno výsledků metrik kódu

**Výsledků metrik kódu** okně se zobrazí data, která je vygenerován nástrojem analýza kódu metriky. Další informace o hodnoty dat metrik kódu najdete v tématu [hodnoty metrik kódu](../code-quality/code-metrics-values.md).

## <a name="display-code-metrics-results"></a>Zobrazení výsledků metrik kódu

**Výsledků metrik kódu** okno se automaticky zobrazí při generování výsledků metrik kódu. Kdykoli můžete také zobrazit okna.

Okno výsledků metrik kódu pomocí jedné z následujících pořadí nabídky můžete zobrazit:

- Na **analyzovat** nabídce zvolte **Windows** > **výsledků metrik kódu**.

- Na **zobrazení** nabídce zvolte **ostatní Windows** > **výsledků metrik kódu**.

**Výsledků metrik kódu** otevře se okno, i v případě, že neobsahuje žádné výsledky.

### <a name="to-view-code-metrics-details"></a>Chcete-li zobrazit podrobnosti metrik kódu

Pokud byly vytvořeny výsledky metrik kódu, rozbalte ve stromu v **hierarchie** sloupce.

## <a name="filter-code-metrics-results"></a>Filtrování výsledků metrik kódu

Můžete filtrovat výsledky, které jsou zobrazeny v **výsledků metrik kódu** pomocí panelu nástrojů v horní části okna. Například můžete chtít zobrazit pouze výsledky, které mají index udržovatelnosti pod 65.

**Filtr** rozevírací seznam obsahuje názvy sloupců výsledky. Když je definována filtr, přidá se do dolní části seznamu spolu s odsazení. Seznam může obsahovat posledních 10 filtry, které byly definovány.

### <a name="to-filter-the-code-metrics-results"></a>K filtrování výsledků metrik kódu

1.  Z **filtr** seznamu, vyberte název sloupce.

2.  V **Min**, zadejte minimální hodnotu, který se má zobrazit.

3.  V **maximální**, zadejte maximální hodnotu, který se má zobrazit.

4.  Klikněte na tlačítko **použít filtr** tlačítko.

5.  Pokud chcete zobrazit podrobnosti výsledku, rozbalte stromovou strukturu hierarchie.

## <a name="add-remove-and-rearrange-data-columns"></a>Přidání, odebrání a změna uspořádání dat sloupců

Můžete přidat nebo odebrat výsledky ze sloupce **výsledků metrik kódu** okna. Kromě toho můžete změnit uspořádání sloupců výsledky tak, aby byly zobrazeny v pořadí, ve kterém chcete.

### <a name="add-or-remove-a-column"></a>Přidat nebo odebrat sloupce

1. Klikněte na tlačítko **Přidat/odebrat sloupce** tlačítko, nebo klikněte pravým tlačítkem na záhlaví libovolného sloupce a potom klikněte na tlačítko **Přidat/odebrat sloupce**.

1. V **Přidat/odebrat sloupce** dialogové okno, zaškrtněte nebo zrušte zaškrtnutí políčka pro sloupec, který chcete přidat nebo odebrat a pak zvolte **OK**.

### <a name="rearrange-columns"></a>Změnit uspořádání sloupců

1. Klikněte na tlačítko **Přidat/odebrat sloupce** tlačítko.

1. V **Přidat/odebrat sloupce** dialogového okna, vyberte sloupec, který chcete přesunout a pak zvolte šipku nahoru nebo šipku dolů.

1. Když sloupec je umístěn, kam chcete, zvolte **OK**.

## <a name="copy-data-to-the-clipboard-or-excel"></a>Kopírování dat do schránky nebo aplikace Excel

Můžete vybrat a kopírovat vybraného řádku dat metrik kódu do schránky jako textový řetězec, který obsahuje jeden řádek pro název a hodnotu každého sloupce data. Můžete také kliknout na **otevřít výběr v aplikaci Microsoft Excel** exportovat všechny výsledky metrik kódu do Excelové tabulky.

## <a name="create-a-work-item-based-on-code-metric-results"></a>Vytvoření pracovní položky na základě výsledků metrik kódu

Můžete vytvořit [panely Azure](/azure/devops/boards/index?view=vsts) výsledkem pracovní položku, která je založena na **výsledků metrik kódu** okna. Po vytvoření pracovní položky sady Visual Studio automaticky zadá název **název** pole a kód dat metrik v části **historie** kartu.

Další informace o Azure panelů pracovní položky, naleznete v tématu [pracovní položky](/azure/devops/boards/work-items/index?view=vsts).

### <a name="to-create-a-work-item-based-on-a-result"></a>Chcete-li vytvořit pracovní položku podle výsledku

1.  Klikněte pravým tlačítkem na výsledek.

2.  Přejděte na **vytvořit pracovní položku**a potom klikněte na typ pracovní položky, kterou chcete vytvořit (**chyb**, **úloh**a tak dále).

3.  Vyplňte formulář pracovní položky vyplnění všech povinných polích.

4.  Na **souboru** nabídky, klikněte na tlačítko **Uložit vše** k uložení pracovní položky.

### <a name="to-create-a-bug-based-on-a-result"></a>Vytvořit chybu na základě výsledku

1.  Klikněte na výsledek a vyberte ji.

2.  Klikněte na tlačítko **vytvořit pracovní položku** tlačítko.

3.  Vyplňte formulář pracovní položky vyplnění všech povinných polích.

4.  Na **souboru** nabídky, klikněte na tlačítko **Uložit vše** k uložení pracovní položky.

## <a name="see-also"></a>Viz také:

- [Hodnoty metrik kódu](../code-quality/code-metrics-values.md)
- [Postupy: Vygenerování dat metrik kódu](../code-quality/how-to-generate-code-metrics-data.md)