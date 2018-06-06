---
title: Vytváření a spouštění testování částí pro aplikace UWP v sadě Visual Studio
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
helpviewer_keywords:
- unit tests, creating
- unit tests
- unit tests, UWP apps
- unit tests, running
ms.author: gewarren
manager: douge
ms.workload:
- uwp
author: gewarren
ms.openlocfilehash: cf27c036f68eb4d2847c1070282c7949f59d2454
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/04/2018
ms.locfileid: "34751712"
---
# <a name="walkthrough-create-and-run-unit-tests-for-uwp-apps"></a>Návod: Vytváření a spouštění testování částí pro aplikace UWP

Visual Studio zahrnuje podporu pro jednotku testování aplikací pro univerzální platformu Windows (UWP). Obsahuje šablony projektů testů jednotek pro Visual C#, Visual Basic a Visual C++.

> [!TIP]
> Další informace o vývoji aplikací UWP najdete v tématu [Začínáme s aplikací UWP](/windows/uwp/get-started/).

Následující postupy popisují postup vytvoření, spuštění a ladění testy částí pro aplikace pro UPW.

## <a name="create-a-unit-test-project-for-a-uwp-app"></a>Vytvoření projektu testů jednotek pro aplikace UWP

1.  Z **soubor** nabídce zvolte **nový projekt**.

     Zobrazí se dialogové okno Nový projekt.

2.  V části šablony vyberte programovací jazyk, který chcete vytvořit testování částí v a potom vyberte, že přidružené univerzální pro Windows jednotkové testování knihovny. Například vyberte **Visual C#** , zvolte **univerzální pro Windows**a potom zvolte **knihovny Test jednotky (Universal Windows)**.

3.  (Volitelné) V **název** textovému poli, zadejte název, kterou chcete použít pro projekt.

4.  (Volitelné) Změňte cestu, kde chcete vytvořit projekt tak, že ho v **umístění** textovému poli, nebo výběrem **Procházet** tlačítko.

5.  (Volitelné) V **řešení** název textového pole, zadejte tento název, kterou chcete použít pro vaše řešení.

6.  Ponechte **vytvořit adresář pro řešení** možnost vybrána a vyberte **OK** tlačítko.

     ![Knihovna testovací šité na míru jednotky](../test/media/unit_test_win8_1.png)

     Průzkumník řešení je naplněna projektu testování částí UWP a editoru kódu zobrazí výchozí testu jednotek s názvem UnitTest1.

     ![Nový projekt test šité na míru jednotky](../test/media/unit_test_win8_unittestexplorer_newprojectcreated.png)

## <a name="edit-the-unit-test-projects-uwp-application-manifest-file"></a>Úprava souboru manifestu aplikace UWP projektu testování částí

1.  V Průzkumníku řešení klikněte pravým tlačítkem myši *Package.appxmanifest* souboru a zvolte **otevřete**.

     Návrhář manifestu zobrazí pro úpravy.

2.  V Návrháři Manifest zvolte **možnosti** kartě.

3.  V seznamu v části **možnosti**, vyberte možnosti, je nutné, vaše testování částí a kód to tak, aby měl testování. Vyberte například **Internet** zaškrtávací políčko, pokud jednotkové testování vyžaduje a kód je testování musí mít možnost přístupu k Internetu.

    > [!NOTE]
    > Možnosti, kterou vyberete by zahrnovat pouze možnosti, které jsou nezbytné pro testování částí, aby správně fungoval.

     ![Manifest testů jednotek](../test/media/unit_test_win8_.png)

## <a name="code-the-unit-test-for-a-uwp-app"></a>Programování testu jednotek pro aplikace UWP

V editoru kódu upravit testování částí a přidat vyhodnotí a logiku potřebnou pro svůj test.

## <a name="run-unit-tests"></a>Spouštění testování částí

### <a name="to-build-the-solution-and-run-the-unit-test-using-test-explorer"></a>Sestavení řešení a spuštění testování částí pomocí Průzkumníka testů

1.  Na **Test** nabídce zvolte **Windows**a potom zvolte **Průzkumníka testů**.

     Testování Explorer zobrazí bez svůj test se uvedené.

2.  Z **sestavení** nabídce zvolte **sestavit řešení**.

     Test jednotky je nyní obsažena.

    > [!NOTE]
    > Musíte sestavit řešení Chcete-li aktualizovat seznam testů jednotek v Průzkumníka testů.

3.  V Průzkumníku otestovat zvolte testování částí, které jste vytvořili.

    > [!TIP]
    > Průzkumníka testů obsahuje odkaz na zdrojový kód do **zdroj:**.

4.  Zvolte **spustit všechny**.

     ![Průzkumníka testů jednotek &#45; spuštění testování částí](../test/media/unit_test_win8_unittestexplorer_contextmenurun.png)

    > [!TIP]
    > Vyberte jeden nebo více testů částí uvedených v Průzkumníku, klikněte pravým tlačítkem a zvolte **spuštění testů vybrané**.
    >
    > Kromě toho můžete **ladění vybrané testy**, **otevřete testovací**a použít **vlastnosti** možnost.
    >
    > ![Průzkumníka testů jednotek &#45; uni testovací kontextové nabídky](../test/media/unit_test_win8_unittestexplorer_contextmenu.png)

    Jednotka test spustí. Po dokončení testování Explorer zobrazí stav testu, uplynulý čas a obsahuje odkaz na zdroj.

    ![Průzkumníka testů jednotek &#45; test byla dokončena](../test/media/unit_test_win8_unittestexplorer_done.png)

## <a name="see-also"></a>Viz také:

- [Testování aplikací pro UWP se sadou Visual Studio](../test/testing-store-apps-with-visual-studio.md)
- [Vytvoření a testování aplikací UWP](/vsts/build-release/apps/windows/universal?tabs=vsts)
