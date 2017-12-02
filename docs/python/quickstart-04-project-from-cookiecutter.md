---
title: "Rychlý úvod: Vytváření projektů v jazyce Python ze šablony Cookiecutter v sadě Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 09/22/2017
ms.reviewer: 
ms.suite: 
ms.technology: devlang-python
ms.devlang: python
ms.tgt_pltfrm: 
ms.topic: article
caps.latest.revision: "1"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.openlocfilehash: 876fdbd4507fd7ed55e7b29834d4a3bc5e68dfad
ms.sourcegitcommit: b7d3b90d0be597c9d01879338dd2678c881087ce
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/01/2017
---
# <a name="quickstart-create-a-project-from-a-cookiecutter-template"></a>Rychlý úvod: Vytvořte projekt ze šablony Cookiecutter

Jakmile jste [nainstalována podpora v jazyce Python ve Visual Studio 2017](installation.md), je snadné vytvořit nový projekt ze šablony Cookiecutter, včetně mnoha z těch, které jsou publikovány na Githubu. [Cookiecutter](https://cookiecutter.readthedocs.io/en/latest/) poskytuje grafické uživatelské rozhraní k zjištění šablony, zadejte možnosti šablony a vytváření projektů a soubory. To je součástí Visual Studio 2017 a je možné nainstalovat odděleně v dřívějších verzích sady Visual Studio.

1. Tento rychlý start nejprve nainstalujte distribuční Anaconda3 Python, včetně nezbytných balíčků Python pro šablonu Cookiecutter zobrazeny zde. Spusťte instalační program sady Visual Studio, vyberte **upravit**, rozbalte položku Možnosti **vývoj Python** na pravé straně a vyberte možnost "Anaconda3" (32bitová nebo 64bitová verze). Všimněte si, že instalace může trvat delší dobu v závislosti na rychlosti sítě Internet, ale toto je nejjednodušší způsob, jak nainstalovat potřebné balíčky.

1. Spusťte sadu Visual Studio.

1. Vyberte **soubor > Nový > z Cookiecutter...** . Tento příkaz otevře okno v sadě Visual Studio, kde je možné procházet šablony. 

    ![Nový projekt ze šablony Cookiecutter](media/projects-from-cookiecutter1.png)

1. Vybraná šablona "Microsoft nebo python-sklearn třídění cookiecutter" a pak vyberte **Další**. (Tento proces může trvat několik minut při prvním použití Cookiecutter.)

1. V dalším kroku, nastavit umístění pro nový projekt v **vytvořit na** pole a pak vyberte **vytvořit**.

    ![Druhý krok pomocí Cookiecutter, nastavení vlastností projektu](media/projects-from-cookiecutter2.png)

1. Po dokončení procesu se zobrazí zpráva "Soubory vytvořen úspěšně." Vyberte příkaz **otevřete v Průzkumníku řešení** otevřít projekt.

1. Stiskněte klávesy Ctrl + F5 nebo vyberte **ladění > Spustit bez ladění** ke spuštění programu. 

    ![Výstup šablony python sklearn třídění cookiecutter projektu](media/projects-from-cookiecutter4.png)


## <a name="next-steps"></a>Další kroky

> [!div class="nextstepaction"]
> [Kurz: Práce s Python v sadě Visual Studio](vs-tutorial-01-01.md)

## <a name="see-also"></a>Viz také

- [Použití rozšíření Cookiecutter](cookiecutter.md)
- [Vytvoření prostředí pro existující překladač Pythonu](python-environments.md#creating-an-environment-for-an-existing-interpreter).
- [Instalace podpory Python v sadě Visual Studio 2015 a starší](installation.md).
- [Umístění instalace](installation.md#install-locations).
