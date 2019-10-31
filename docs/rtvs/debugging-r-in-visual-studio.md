---
title: Ladění kódu R
description: Sada Visual Studio poskytuje úplné ladicí prostředí pro R, včetně zarážek, připojení, zásobníku volání a kontrol proměnných.
ms.date: 01/24/2018
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: jillfra
ms.workload:
- data-science
ms.openlocfilehash: 5efa0a32f51e1f5060474a0d277bfca7f1e7d548
ms.sourcegitcommit: 40bd5b27f247a07c2e2514acb293b23d6ce03c29
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2019
ms.locfileid: "73189252"
---
# <a name="debug-r-in-visual-studio"></a>Ladění R v aplikaci Visual Studio

Nástroje R pro Visual Studio (RTVS) se integruje s plným prostředím ladění sady Visual Studio (viz [ladění v aplikaci Visual Studio](../debugger/debugger-feature-tour.md). Tato podpora zahrnuje zarážky, připojení ke spuštěným procesům, kontrolu a sledování proměnných a kontrolu zásobníku volání. Tento článek popisuje tyto aspekty ladění, které jsou jedinečné pro R a RTVS.

Spuštění ladicího programu pro spouštěcí soubor R v projektu R je stejné jako u jiných typů projektů **: použijte ladění** > **Spustit ladění**, klávesu **F5** nebo **zdrojový spouštěcí soubor** na panelu nástrojů ladění:

![Tlačítko pro spuštění ladicího programu pro R](media/debugger-start-button.png)

Chcete-li změnit spouštěcí soubor, klikněte pravým tlačítkem myši na soubor v Průzkumník řešení a vyberte možnost **nastavit jako spouštěcí skript jazyka R**.

Ve všech případech spustí ladicí program "sources" soubor v interaktivním okně, což znamená, že ho načte a spustí, jak je znázorněno ve výstupu interaktivního okna:

```output
> rtvs::debug_source("c:/proj/rproject1/rproject1/script.R")
Sourcing: c:\proj\rproject1\rproject1\script.R
Sourcing: c:\proj\rproject1\rproject1\Settings.R
```

Všimněte si, že funkce `rtvs::debug_source` se používá ke zdroji skriptu. Tato funkce je povinná, protože RTVS potřebuje upravit kód v přípravě pro ladění. Při použití libovolného RTVSého příkazu a k připojení ladicího programu Visual Studio automaticky používá `rtvs::debug_source`.

Ladicí program můžete také ručně připojit z interaktivního okna přímo pomocí příkazu > **nástroje R** > **relace** **připojit ladicí program** **, > ** **připojit k interaktivní RMU** příkazu nebo Příkaz **připojit ladicí program** na panelu nástrojů interaktivního okna. Až to uděláte, je vaše zodpovědnost za zdroj souborů, které chcete ladit. Pokud chcete soubory vytvořit ručně, ujistěte se, že používáte `rtvs::debug_source` a ne regulární `source` příkaz v jazyce R.

Toto připojení mezi ladicím programem a interaktivním oknem usnadňuje provádění akcí, jako je volání (a ladění) funkce s různými hodnotami parametrů. Předpokládejme například, že máte následující funkci ve zdrojovém souboru (to znamená, že je načten do relace):

```R
add <- function(x, y) {
    return(x + y)
}
```

Pak nastavíte zarážku na příkaz `return`. V interaktivním okně teď zadáte `add(4,5)` zastaví ladicí program na zarážce.

## <a name="environment-browser-in-the-interactive-window"></a>Prohlížeč prostředí v interaktivním okně

Když jste v ladicím programu zastavili, zastaví se také v okně [interaktivní okno](interactive-repl-for-r-in-visual-studio.md)s výzvou v prohlížeči prostředí. Výzva se zobrazí jako `Browse[n]>`, kde n je číslo.

Prohlížeč prostředí podporuje řadu speciálních příkazů:

| Příkaz | Popis |
| --- | --- |
| N | Další: spustí další příkaz v souboru kódu (totéž jako krok over). |
| s | Krok do: spustí další příkaz v souboru kódu, krokování do oboru funkce, pokud je dalším příkazem volání funkce. |
| FJ | dokončit: spustí zbytek aktuálního rozsahu funkcí a vrátí volajícímu (stejné jako krok ven). |
| c, pokračování | pokračovat: spustí program na další zarážku. |
| Q | konec: ukončí relaci ladění. |
| kde | Zobrazit zásobník: zobrazí zásobník volání v interaktivním okně. |
| Nápověda | Zobrazit Help: zobrazí dostupné příkazy v interaktivním okně. |
| výraz &lt;&gt; | vyhodnotit výraz *ve výrazu*. |

![Prohlížeč prostředí v interaktivním okně](media/debugger-environment-browser.png)
