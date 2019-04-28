---
title: Použití legendy zobrazení grafů k analýze zátěžových testů
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- Load Test Analyzer, graphs view legend
- load tests, graphs view legend
ms.assetid: 0f6ba8e4-1343-419c-8a9f-240cf50efed7
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 4c29620cad3333144d65386e509339e2f5eccddf
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62562655"
---
# <a name="use-the-graphs-view-legend-to-analyze-load-tests"></a>Použití legendy zobrazení grafů k analýze zátěžových testů

Zobrazení grafů Analyzéru zátěžového testu obsahuje panel legendy, jenž zobrazuje informace pro každý čítač výkonu, který je přidružen k aktuálně vybranému grafu.

![Legenda zobrazení grafů](../test/media/load_viewlegend.png)

[!INCLUDE [web-load-test-deprecated](includes/web-load-test-deprecated.md)]

Legenda obsahuje následující informace:

- **Zobrazit v grafu:** Pomocí těchto zaškrtávacích políček k určení, zda řádek pro konkrétní čítač, jako například **uživatelské zatížení** nebo **chyby/s**, vykreslit v grafu. Vyberte zaškrtávací políčko, pokud chcete řádek vykreslit v grafu. Zrušte zaškrtnutí políčka pro odebrání řádku vykreslení grafu. I po odstranění čáry grafu zůstane statistika čítače nadále zobrazena v legendě.

- **Rozsah:** Tento sloupec zobrazuje rozsah čítače výkonu osy y. Ve výchozím nastavení tato hodnota automaticky upraví jako rozsah změny ukázková data. Automaticky upravený rozsah bude vždy o další mocninu desíti větší než maximální hodnota, včetně záporných mocnin desíti. Graf může obsahovat mnoho různých čítačů, z nichž každý má jiný rozsah. Osa y tedy není popsána žádným konkrétním rozsahem. Namísto toho je popsána hodnotami 0 až 100 představujícími procento celkového rozsahu každého čítače. Například pro čítač s rozsahem 1000 by datový bod 60 na ose y odpovídal hodnotě čítače 600.

    > [!NOTE]
    > Úpravy hodnot automatického rozsahu můžete vypnout podle rozsahu na určitou hodnotu. Je-li rozsah uzamčen, jsou všechny hodnoty přesahující tento rozsah zobrazeny jako maximální hodnota zadaná v horní části grafu. Použití **možnosti grafu** dialogové okno k uzamčení rozsah na konkrétní hodnotu.

- **Čítače:** Čtyři sloupce pojmenované **čítač**, **Instance**, **kategorie**, a **počítače** dohromady jedinečně identifikují čítač výkonu.

- **Barva:** **Barva** sloupci se zobrazuje barvu a styl čáry možná vykreslená čáry pro čítač výkonu. Použití **možnosti grafu** dialogové okno změnit barvu nebo řádek styl čítače výkonu v grafu. **Možnosti grafu** dialogové okno je k dispozici z místní nabídky legendy.

- **Statistiky:** **Min**, **maximální**, **Avg** a **poslední** sloupce zobrazují příslušné statistiky čítače výkonu. Tyto hodnoty odpovídají data, která se zobrazí na viditelné oblasti grafu. Pokud například přiblížíte zobrazení na nějakou oblast běhu, statistika legendy bude odpovídat hodnotám platným pouze pro přiblíženou oblast. "Posledního" sloupce je hodnota čítače výkonu v nedávno provedených intervalu vzorkování.

    > [!NOTE]
    > Sloupec Poslední se zobrazí v legendě Analyzéru zátěžového testu pouze za běhu zátěžového testu.

     Další informace najdete v tématu [jak: Přiblížení oblasti grafu](../test/how-to-zoom-in-on-a-region-of-the-graph-in-load-test-results.md).

Výběr položky v legendě provede následující:

- Umožňuje položky k odebrání z legendy a graf. Buď klikněte pravým tlačítkem na položku a vyberte **odstranit**, nebo stisknutím klávesy **odstranit** klíč.

- Zvýrazní možná vykreslená řádek v grafu.

- Způsobí, že datovou mřížku zobrazení dat pro vybranou položku.

- Umožňuje přístup **možnosti grafu** dialogové okno pro čítač.

> [!TIP]
> Můžete použít **rozevíracího seznamu Možnosti grafu** tlačítko **Analyzéru zátěžového testu** nástrojů a vyberte **zobrazit legendu** zobrazení nebo skrytí **legendy** panel, který je přidružený k zobrazení grafu.

## <a name="see-also"></a>Viz také:

- [Postupy: Přiblížení oblasti grafu](../test/how-to-zoom-in-on-a-region-of-the-graph-in-load-test-results.md)
- [Analýza výsledků zátěžových testů v zobrazení grafů](../test/analyze-load-test-results-in-the-graphs-view.md)
