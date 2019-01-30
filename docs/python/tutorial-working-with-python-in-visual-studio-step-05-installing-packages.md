---
title: Python v sadě Visual Studio kurz – krok 5 instalace balíčků
titleSuffix: ''
description: Krok 5 průvodce základní funkce Pythonu v sadě Visual Studio, ukázka funkce aplikace Visual Studio pro správu balíčků v prostředí Pythonu.
ms.date: 01/28/2019
ms.prod: visual-studio-dev15
ms.topic: tutorial
author: kraigb
ms.author: kraigb
manager: jillfra
ms.custom: seodec18
ms.workload:
- python
- data-science
ms.openlocfilehash: 7df99346d30c4255aaf9c08648f185b732c3ae32
ms.sourcegitcommit: a916ce1eec19d49f060146f7dd5b65f3925158dd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/29/2019
ms.locfileid: "55231399"
---
# <a name="step-5-install-packages-in-your-python-environment"></a>Krok 5: Instalace balíčků ve vašem prostředí Pythonu

**Předchozí krok: [Spuštění kódu v ladicím programu](tutorial-working-with-python-in-visual-studio-step-04-debugging.md)**

Komunita vývojářů Python vytvořil tisíce užitečné balíčky, které můžete začlenit do vašich projektů. Visual Studio poskytuje uživatelské rozhraní pro správu balíčků ve vašem prostředí Pythonu.

1. Vyberte **zobrazení** > **ostatní Windows** > **prostředí Pythonu** příkazu nabídky. **Prostředí Pythonu** jako partnera, který se otevře okno **Průzkumníka řešení** a zobrazí se vám různá prostředí, které jsou k dispozici. Seznam obsahuje i prostředí, které jste si nainstalovali pomocí instalačního programu sady Visual Studio a ty, které můžete nainstalovat samostatně. Prostředí tučným písmem je výchozí prostředí, který se používá pro nové projekty.

   ![Okno prostředí Pythonu](media/environments-default-view-blue.png)

2. Prostředí **přehled** karta poskytuje rychlý přístup k **interaktivní** okna pro toto prostředí spolu s instalační složku a interpretů životní prostředí. Vyberte například **otevřít interaktivní okno** a **interaktivní** v sadě Visual Studio se zobrazí okno pro konkrétní prostředí.

3. Vyberte **balíčky** kartě a můžete zobrazit seznam balíčků, které jsou aktuálně nainstalované ve prostředí.

   ![Balíčky nainstalované ve prostředí](media/environments-installed-packages-blue.png)

4. Nainstalujte `matplotlib` tak, že do vyhledávacího pole zadáte její název, vyberte **instalace pip**

   ![Instalace matplotlib v prostředí](media/environments-add-matplotlib1.png)

5. Pokud se zobrazí výzva k tomu vyjádřit souhlas ke zvýšení úrovně oprávnění.

6. Po dokončení instalace balíčku se zobrazí v **prostředí Pythonu** okna. **X** napravo od balíček odinstaluje se.

   ![Dokončení instalace matplotlib v prostředí](media/environments-add-matplotlib2.png)

   Indikátor průběhu malé se můžou objevit pod prostředí k označení, že Visual Studio sestavuje své databáze IntelliSense pro nově nainstalovaný balíček. **IntelliSense** karta zobrazuje také podrobnější informace. Všimněte si, že než tuto databázi se dokončí, funkce technologie IntelliSense, jako je automatické dokončování a kontroly syntaxe nebudou aktivní v okně editor pro tento balíček.

   Všimněte si, že **Visual Studio 2017 verze 15.6** později používá jiný a rychlejší způsob pro práci s podporou technologie IntelliSense a zobrazí zprávu o tom on **IntelliSense** kartu.

7. Vytvoření nového projektu s **souboru** > **nový** > **projektu**, vyberete **aplikace v Pythonu** Šablona. V souboru kódu, který se zobrazí vložte následující kód, který vytvoří pouze v tomto případě promítají graficky kosinus wave jako předchozí kurz kroky:

    ```python
    from math import radians
    import numpy as np     # installed with matplotlib
    import matplotlib.pyplot as plt

    def main():
        x = np.arange(0, radians(1800), radians(12))
        plt.plot(x, np.cos(x), 'b')
        plt.show()

    main()
    ```

8. Spusťte program s (**F5**) nebo bez ladicího programu (**Ctrl**+**F5**) k zobrazení výstupu:

   ![Výstup příkladu matplotlib](media/environments-add-matplotlib3.png)

## <a name="next-step"></a>Další krok

> [!div class="nextstepaction"]
> [Práce s Gitem](tutorial-working-with-python-in-visual-studio-step-06-working-with-git.md)

## <a name="go-deeper"></a>Seznamte se blíž

- [Prostředí Pythonu](managing-python-environments-in-visual-studio.md)
