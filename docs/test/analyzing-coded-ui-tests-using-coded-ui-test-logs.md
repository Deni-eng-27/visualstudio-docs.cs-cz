---
title: Analýza programových testů uživatelského rozhraní pomocí protokolů z těchto testů
ms.date: 11/04/2016
ms.topic: conceptual
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
author: mikejo5000
ms.openlocfilehash: 6bbb3e6599ef4ae26740eed0eb79047c49356374
ms.sourcegitcommit: 4ae5e9817ad13edd05425febb322b5be6d3c3425
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/11/2020
ms.locfileid: "90036142"
---
# <a name="analyzing-coded-ui-tests-using-coded-ui-test-logs"></a>Analýza programových testů uživatelského rozhraní pomocí protokolů kódovaného testu uživatelského rozhraní

Protokoly programových testů uživatelského rozhraní filtr a zaznamenávají důležité informace o běhu programového testu uživatelského rozhraní. Protokoly se zobrazí ve formátu, který umožňuje rychle ladit problémy.

[!INCLUDE [coded-ui-test-deprecation](includes/coded-ui-test-deprecation.md)]

## <a name="step-1-enable-logging"></a>Krok 1: povolení protokolování

V závislosti na vašem scénáři použijte k povolení protokolu jednu z následujících metod:

- Pokud se v testovacím projektu nenachází žádný *App.config* soubor:

   1. Určete, který proces *QTAgent \* . exe* se spustí při spuštění testu. Jedním ze způsobů, jak to provést, je sledovat kartu **Podrobnosti** ve **Správci úloh**systému Windows.

   2. Otevřete odpovídající soubor *. config* ze složky *% ProgramFiles (x86)% \ Microsoft Visual Studio \\ \<version> \\ \<edition> \Common7\IDE* . Pokud se například proces, který spouští, *QTAgent_40.exe*, otevřete *QTAgent_40.exe.config*.

   2. Změňte hodnotu **EqtTraceLevel** na úroveň protokolu, kterou chcete.

      ```xml
      <!-- You must use integral values for "value".
           Use 0 for off, 1 for error, 2 for warn, 3 for info, and 4 for verbose. -->
      <add name="EqtTraceLevel" value="4" />
      ```

   3. Soubor uložte.

- Pokud je v testovacím projektu přítomen soubor *App.config* :

  - Otevřete soubor *App.config* v projektu a přidejte následující kód pod uzel Konfigurace:

    ```xml
    <system.diagnostics>
      <switches>
        <add name="EqtTraceLevel" value="4" />
      </switches>
    </system.diagnostics>`
    ```

- Povolit protokolování z samotného testovacího kódu:

   ```csharp
   Microsoft.VisualStudio.TestTools.UITesting.PlaybackSettings.LoggerOverrideState = HtmlLoggerState.AllActionSnapshot;
   ```

## <a name="step-2-run-your-coded-ui-test-and-view-the-log"></a>Krok 2: spuštění kódovaného testu uživatelského rozhraní a zobrazení protokolu

Při spuštění programového testu uživatelského rozhraní s úpravami * \*.exe.configho souboru QTAgent * se zobrazí odkaz na výstup v **Průzkumníku testů** . Soubory protokolu se vytvářejí nejen v případě, že se test nezdařil, ale také pro úspěšné testy, pokud je úroveň trasování nastavena na **verbose**.

1. V nabídce **test** zvolte **okna** a pak vyberte **Průzkumník testů**.

2. V nabídce **sestavení** klikněte na příkaz **Sestavit řešení**.

3. V **Průzkumníku testů**vyberte programový test UI, který chcete spustit, otevřete místní nabídku a zvolte možnost **Spustit výběr testů**.

     Automatizované testy se spouštějí a označují, jestli byly úspěšné nebo neúspěšné.

    > [!TIP]
    > Chcete-li zobrazit **Průzkumníka testů**, zvolte možnost **test**  >  **systému Windows**a pak zvolte možnost **Průzkumník testů**.

4. Vyberte odkaz **výstup** ve výsledcích **Průzkumníka testů** .

     ![Odkaz na výstup v Průzkumníku testů](../test/media/cuit_htmlactionlog1.png)

     Tím se zobrazí výstup testu, který obsahuje odkaz na protokol akcí.

     ![Odkazy na výsledky a výstupy ze kódovaného testu uživatelského rozhraní](../test/media/cuit_htmlactionlog2.png)

5. Vyberte odkaz *UITestActionLog.html* .

     Protokol se zobrazí ve webovém prohlížeči.

     ![Soubor protokolu programového testu UI](../test/media/cuit_htmlactionlog3.png)

## <a name="see-also"></a>Viz také

- [Použití automatizace uživatelského rozhraní k otestování kódu](../test/use-ui-automation-to-test-your-code.md)
- [Postupy: spuštění testů z Microsoft Visual Studio](/previous-versions/ms182470(v=vs.140))