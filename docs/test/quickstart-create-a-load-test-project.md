---
title: Vytvořte projekt testu výkonu a zatížení webu
ms.date: 03/14/2018
ms.topic: quickstart
helpviewer_keywords:
- load testing, quickstart
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 7c6f8a7ceb24e6108e5604d9e862527880431b5b
ms.sourcegitcommit: 3d37c2460584f6c61769be70ef29c1a67397cf14
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/21/2019
ms.locfileid: "58324827"
---
# <a name="quickstart-create-a-load-test-project"></a>Rychlý start: Vytvoření projektu pro zátěžový test

V tomto rychlém startu během 10 minut dozvíte, jak vytvořit a spustit webový výkon a projekt zátěžového testu v sadě Visual Studio. Zátěžové testy spustit webového výkonu nebo jednotkových testů ke simulace mnoha uživatelů přistupujících na server ve stejnou dobu.

[!INCLUDE [web-load-test-deprecated](includes/web-load-test-deprecated.md)]

## <a name="software-requirements"></a>Požadavky na software

Projekty testů webového výkonu a zatížení jsou dostupné jenom v edici Enterprise systému Visual Studio.

## <a name="install-the-load-testing-component"></a>Nainstalujte zátěžového testování součástí

Pokud nemáte již výkonu webu a načíst testování nainstalována součást nástroje, bude nutné ji nainstalovat pomocí instalačního programu sady Visual Studio.

1. Otevřít **instalační program sady Visual Studio** z **Start** nabídku Windows. Se dostanete také ho v sadě Visual Studio z **nový projekt** dialogové okno, nebo výběrem **nástroje** > **stažení nástrojů a funkcí** z řádku nabídek.

1. V **instalační program sady Visual Studio**, zvolte **jednotlivé komponenty** kartu a přejděte dolů k položce **ladění a testování** oddílu. Vyberte **výkonnosti webů a zátěžové testování nástroje**.

   ![Výkonnosti webů a zátěžové testování součást nástroje](media/web-perf-load-testing-tools-component.png)

1. Zvolte **změnit** tlačítko.

   Je nainstalován webový výkon a zátěžové testování součástí nástroje.

## <a name="create-a-load-test-project"></a>Vytvoření projektu zátěžového testu

V této části vytvoříme C# projekt zátěžového testu. Můžete také vytvořit projektu jazyka Visual Basic zátěžového testu, pokud dáváte přednost.

::: moniker range="vs-2017"

1. Otevřít Visual Studio.

2. Zvolte **souboru** > **nový** > **projektu** z řádku nabídek.

   **Nový projekt** zobrazí se dialogové okno.

3. V **nový projekt** dialogového okna rozbalte **nainstalováno** a **Visual C#** a pak vyberte **Test** kategorie. Zvolte **webový výkon a projekt zátěžového testu** šablony.

   ![Šablona projektu test webového výkonu a zatížení](media/web-perf-load-test-project-template.png)

4. Zadejte název projektu, pokud nechcete použít výchozí název a klikněte na tlačítko **OK**.

::: moniker-end

::: moniker range=">=vs-2019"

1. Otevřít Visual Studio.

2. V okně start zvolte **vytvořte nový projekt**.

3. V **vytvořte nový projekt** dialogové okno, zadejte **webového testu** do vyhledávacího pole a pak vyberte **webový výkon a projekt zátěžového testu \[zastaralé]** Šablona pro C#. Zvolte **Další**.

4. Zadejte název projektu, pokud nechcete použít výchozí název a klikněte na tlačítko **vytvořit**.

::: moniker-end

   Visual Studio vytvoří projekt a zobrazí soubory v **Průzkumníka řešení**. Projekt zpočátku obsahuje jeden soubor webového testu s názvem *WebTest1.webtest*.

## <a name="add-a-load-test-to-the-project"></a>Přidejte zátěžový test do projektu

1. Z místní nabídky nebo místní nabídku uzlu projektu v **Průzkumníka řešení**, zvolte **přidat** > **zátěžový Test**.

   **Průvodce novým zátěžovým testem** otevře.

1. Vyberte **On-premises zátěžový Test** možnost a klikněte na tlačítko **Další**. Další informace o cloudové zátěžové testování [tady](/azure/devops/test/load-test/get-started-simple-cloud-load-test?view=vsts).

   ![Průvodce novým zátěžovým testem – první stránka](media/load-test-wizard-page-1.png)

1. Zvolte **Další** krokovat průvodce, dokud se nedostanete **přidáte testy do scénáře zátěžového testu a upravit poměr testů** stránky. Zvolte **přidat** tlačítko.

   **Přidat testy** zobrazí se dialogové okno.

1. V části **dostupné testy**vyberte **WebTest1**a klikněte na tlačítko se šipkou doprava přesunout do **vybrané testy** pole. Zvolte **OK** tlačítko.

   ![Přidat testy – dialogové okno](media/add-tests-dialog-box.png)

1. Zpátky **Průvodce novým zátěžovým testem**, zvolte **Dokončit** tlačítko.

   Zátěžový test je přidán do projektu a soubor zátěžového testu se otevře v okně editoru.

## <a name="run-the-load-test"></a>Spusťte zátěžový test

Vytvořili jsme zátěžový test, který nebude provádět velmi dobře, ale přesto ji můžeme spustit.

V místní nabídce nebo kontextové nabídky, která je otevřená v editoru zátěžového testu zvolte **spustit zátěžový Test**.

![Nabídka běhu zátěžového testu](media/run-load-test.png)

Zátěžový test začíná běžet. **Výsledky testu** okno zobrazuje, že probíhá test a analyzéru zátěžového testu se zobrazí v okně editoru. Po dokončení testu, které by měly být pět minut, pokud je přijmout výchozí hodnoty, souhrn se zobrazí v editoru. Můžete zvolit **grafy**, **tabulky**, nebo **podrobností** různé informace o výsledcích zátěžového testu.

![Okno analyzátoru zátěžového testu](media/load-test-analyzer.png)

## <a name="next-steps"></a>Další kroky

Teď, když jste vytvořili projekt jednoduché zátěžového testu, dalším krokem je konfigurace pro scénáře, sad čítačů a parametrů spuštění.

> [!div class="nextstepaction"]
> [Upravit nastavení testu](edit-load-tests.md)
