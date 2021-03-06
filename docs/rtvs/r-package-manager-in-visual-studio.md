---
title: Správce balíčků pro R
description: Jak použít Správce balíčků R v aplikaci Visual Studio k instalaci a správce R balíčků.
ms.date: 01/24/2018
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: jillfra
ms.workload:
- data-science
ms.openlocfilehash: d35bfd45e862912ff78ae600eed01ce8dc002493
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "62998854"
---
# <a name="package-manager"></a>Správce balíčků

Správce balíčků Nástroje R pro Visual Studio (RTVS) je uživatelské rozhraní pro správu balíčků R. Chcete-li jej otevřít, vyberte možnost **nástroje R**  >  balíčky**systému Windows**  >  **Packages** nebo stiskněte **klávesu CTRL** + **7**.

Správce balíčků obsahuje tři karty. Na každé kartě se zobrazí seznam relevantních balíčků na levé straně a konkrétní podrobnosti pro vybraný balíček na pravé straně, včetně verze balíčku, popisu, licence, umístění instalace a odkazů na další relevantní informace. Vyhledávací pole v pravém horním rohu umožňuje filtrovat seznam.

> [!Tip]
> Termín v poli hledání zůstane v platnosti při přepínání mezi kartami.

- **K dispozici** můžete procházet balíčky, které chcete nainstalovat. Pokud je balíček již nainstalován, tlačítko **nainstalovat** na pravé straně se změní na **odinstalace**.

    ![Karta dostupné balíčky ve Správci balíčků Nástroje R pro Visual Studio](media/package-manager-available.png)

- **Nainstalované** : zobrazí všechny nainstalované a načtené balíčky. Zelená tečka vedle balíčku označuje, že je načten do relace jazyka R. K odinstalaci balíčku se dá použít červená ikona X v levém seznamu nebo tlačítko **odinstalovat** na pravé straně. Pokud je k dispozici novější verze nainstalovaného balíčku, provede se aktualizace modrou šipkou na pravé straně balíčku.

    ![Karta nainstalované balíčky ve Správci balíčků Nástroje R pro Visual Studio](media/package-manager-installed.png)

- **Načtené** zobrazí jenom balíčky, které se načtou do relace jazyka R. všechny se zobrazí se zelenou tečkou. Balíčky taky můžete odinstalovat a aktualizovat tady.

    ![Karta načtené balíčky ve Správci balíčků Nástroje R pro Visual Studio](media/package-manager-loaded.png)

## <a name="package-locations"></a>Umístění balíčků

Balíčky jsou nainstalovány v následujících umístěních:

- Balíčky Core, které jsou součástí RTVS, jsou nainstalované v adresáři *C:\Program Files\Microsoft\R Client \ R_SERVER \Library*
- Další balíčky se nainstalují do *%USERPROFILE%\Documents\R\win-library\3.3* .
