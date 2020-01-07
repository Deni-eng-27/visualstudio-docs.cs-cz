---
title: Testování jednotek kódu Visual C#
ms.date: 09/27/2019
ms.topic: conceptual
ms.author: mikejo
author: mikejo5000
manager: jillfra
ms.workload:
- uwp
ms.openlocfilehash: 31fbbfaa5d16dd51776f592b89a7846936b3013f
ms.sourcegitcommit: d233ca00ad45e50cf62cca0d0b95dc69f0a87ad6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/01/2020
ms.locfileid: "75590862"
---
# <a name="unit-test-c-code"></a>Test jednotek kódu C#

Tento článek popisuje jeden ze způsobů, jak vytvořit testy jednotek C# pro třídu v aplikaci pro UWP.

**Kořenová** třída, která je zkoušenou třídou, implementuje funkci, která vypočítá odhad druhé odmocniny daného čísla.

Tento článek ukazuje *Vývoj řízený testováním*. V tomto přístupu nejprve zapíšete test, který ověří konkrétní chování v systému, který testujete, a potom napíšete kód, který projde testem.

## <a name="create-the-solution-and-the-unit-test-project"></a>Vytvoření řešení a projektu testování částí

1. Na **souboru** nabídce zvolte **nový** > **projektu**.

2. Vyhledejte a vyberte šablonu projektu **prázdná aplikace (univerzální pro Windows)** .

3. Pojmenujte **matematiky**projektu.

4. V **Průzkumník řešení**klikněte pravým tlačítkem na řešení a vyberte **Přidat** > **Nový projekt**.

5. Vyhledejte a vyberte šablonu projektu **aplikace pro testování jednotek (univerzální pro Windows)** .

6. Pojmenujte projekt testů **RooterTests**.

## <a name="verify-that-the-tests-run-in-test-explorer"></a>Ověřte, že testy spustit v Průzkumníku testů

1. Do souboru *UnitTest.cs* Vložte nějaký kód testu do **TestMethod1** :

   ```csharp
   [TestMethod]
   public void TestMethod1()
   {
       Assert.AreEqual(0, 0);
   }
   ```

   Třída <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> poskytuje několik statických metod, které lze použít k ověření výsledků v testovacích metodách.

::: moniker range="vs-2017"

2. V nabídce **test** vyberte možnost **Spustit** > **všechny testy**.

::: moniker-end

::: moniker range=">=vs-2019"

2. V nabídce **test** vyberte možnost **Spustit všechny testy**.

::: moniker-end

   Testovací projekt vytvoří a spustí. Být pacient, protože může chvíli trvat. **Průzkumníka testů** okno a test je uvedený v části **úspěšné testy**. **Souhrn** poskytuje další podrobnosti o vybrané testovací podokno v dolní části okna.

## <a name="add-the-rooter-class-to-the-maths-project"></a>Přidat třídu Rooter matematické výrazy projektu

1. V **Průzkumník řešení**klikněte pravým tlačítkem myši na projekt **matematického** typu a zvolte možnost **Přidat** > **třídu**.

2. Název souboru třídy *Rooter.cs*.

3. Do souboru *Rooter.cs* třídy **root** přidejte následující kód:

   ```csharp
   public Rooter()
   {
   }

   // estimate the square root of a number
   public double SquareRoot(double x)
   {
       return 0.0;
   }
   ```

   Třída **Rooter** deklaruje konstruktor a metodu **SquareRoot** Estimator. Metoda **SquareRoot** je pouze minimální implementace, stačí pouze k otestování základní struktury nastavení testování.

4. Přidejte klíčové slovo `public` do deklarace třídy **Rooter** , aby k němu mohl přistupovat testovací kód.

   ```csharp
   public class Rooter
   ```

## <a name="add-a-project-reference"></a>Přidat odkaz na projekt

1. Přidejte odkaz z projektu RooterTests do aplikace Maths.

    1. V **Průzkumník řešení**klikněte pravým tlačítkem na projekt **RooterTests** a pak zvolte **Přidat** > **odkaz**.

    2. V **přidat odkaz - RooterTests** dialogového okna rozbalte **řešení** a zvolte **projekty**. Vyberte projekt **matematiky** .

        ![Přidat odkaz na projekt matematické výrazy](../test/media/ute_cs_windows_addreference.png)

2. Do souboru *UnitTest.cs* přidejte příkaz `using`:

    1. Otevřete *UnitTest.cs*.

    2. Přidejte tento kód níže `using Microsoft.VisualStudio.TestTools.UnitTesting;` řádku:

       ```csharp
       using Maths;
       ```

3. Přidejte test, který používá funkci **root** . Do *UnitTest.cs*přidejte následující kód:

   ```csharp
   [TestMethod]
   public void BasicTest()
   {
       Maths.Rooter rooter = new Rooter();
       double expected = 0.0;
       double actual = rooter.SquareRoot(expected * expected);
       double tolerance = .001;
       Assert.AreEqual(expected, actual, tolerance);
   }
   ```

   Nový test se zobrazí v **Průzkumníka testů** v **nespuštěné testy** uzlu.

4. Aby nedošlo k chybě "datová část obsahuje dva nebo více souborů se stejnou cílovou cestou", v **Průzkumník řešení**rozbalte uzel **vlastnosti** v projektu **matematické** hodnoty a pak odstraňte soubor *Default. Rd. XML* .

::: moniker range="vs-2017"

6. V **Průzkumník testů**, zvolte **spustit všechny**.

   Řešení se sestaví a spustí a projde testy.

   ![BasicTest předané v Průzkumníku testů](../test/media/ute_cpp_testexplorer_basictest.png)

::: moniker-end

::: moniker range=">=vs-2019"

6. V **Průzkumníku testů**vyberte možnost **Spustit všechny testy**.

   Řešení se sestaví a spustí a projde testy.

   ![V Průzkumníku testů byl úspěšný základní test.](../test/media/vs-2019/test-explorer-uwp-app.png)

::: moniker-end

Nastavili jste projekty testů a aplikací a ověřili, že můžete spouštět testy, které volají funkce v projektu aplikace. Teď můžete začít psát skutečné testů a kódu.

## <a name="iteratively-augment-the-tests-and-make-them-pass"></a>Využívejte iterativní posílit testy a daly se předat

1. Přidejte nový test s názvem **RangeTest**:

   ```csharp
   [TestMethod]
   public void RangeTest()
   {
       Rooter rooter = new Rooter();
       for (double v = 1e-6; v < 1e6; v = v * 3.2)
       {
           double expected = v;
           double actual = rooter.SquareRoot(v*v);
           double tolerance = expected/1000;
           Assert.AreEqual(expected, actual, tolerance);
       }
   }
   ```

   > [!TIP]
   > Doporučujeme neměňte testy, které prošly. Místo toho přidejte nový test.

2. Spusťte test **RangeTest** a ověřte, zda se nezdařila.

   ![RangeTest selže](../test/media/ute_cpp_testexplorer_rangetest_fail.png)

   > [!TIP]
   > Ihned po zápisu testu spusťte jej a ověřte, zda se nezdařila. To umožňuje vyhnout se snadno chybu zápisu test, který se nikdy selže.

3. Vylepšete testovaného kódu tak, aby nový test byl úspěšný. Změňte funkci **SquareRoot** v *Rooter.cs* na tuto:

   ```csharp
   public double SquareRoot(double x)
   {
       double estimate = x;
       double diff = x;
       while (diff > estimate / 1000)
       {
           double previousEstimate = estimate;
           estimate = estimate - (estimate * estimate - x) / (2 * estimate);
           diff = Math.Abs(previousEstimate - estimate);
       }
       return estimate;
   }
   ```

::: moniker range="vs-2017"

4. V **Průzkumník testů**, zvolte **spustit všechny**.

::: moniker-end

::: moniker range=">=vs-2019"

4. V **Průzkumníku testů**vyberte možnost **Spustit všechny testy**.

::: moniker-end

   Všechny tři testy jsou nyní úspěšné.

> [!TIP]
> Vývoj kódu tak, že přidáte testy jeden po druhém. Ujistěte se, že všechny testy jsou úspěšné po každé iteraci.

## <a name="refactor-the-code"></a>Refaktorování kódu

V této části provedete refaktorování aplikace a testovací kód, potom znovu spustíte testy, abyste se ujistili, že jsou stále předávány.

### <a name="simplify-the-square-root-estimation"></a>Zjednodušení čtvercového odhadu

1. Zjednodušte centrální výpočet ve funkci **SquareRoot** , a to tak, že změníte jeden řádek kódu, a to takto:

    ```csharp
    // Old code
    //estimate = estimate - (estimate * estimate - x) / (2 * estimate);

    // New code
    estimate = (estimate + x/estimate) / 2.0;
    ```

2. Spusťte všechny testy a ujistěte se, že jste nepředstavili regresi. Všechny by měly být passované.

> [!TIP]
> Se spouští stabilní sada testů jednotek dobré poskytuje jistotu, že nebyly zavedeny chyby při změně kódu.

### <a name="eliminate-duplicated-code"></a>Eliminovat duplicitní kód

Metoda **RangeTest** pevně vystaví jmenovatel proměnné *tolerance* , která je předána metodě <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert>. Pokud plánujete přidat další testy, které používají stejný výpočet tolerance, použití pevně zakódované hodnoty ve více umístěních usnadňuje údržbu kódu.

1. Přidejte soukromou pomocnou metodu do třídy **UnitTest1** pro výpočet hodnoty tolerance a pak zavolejte tuto metodu z **RangeTest**.

    ```csharp
    private double ToleranceHelper(double expected)
    {
        return expected / 1000;
    }

    ...

    [TestMethod]
    public void RangeTest()
    {
        ...
        // Old code
        // double tolerance = expected/1000;

        // New code
        double tolerance = ToleranceHelper(expected);
    }
    ...
    ```

2. Spusťte **RangeTest** a ujistěte se, že se pořád ještě projde.

> [!TIP]
> Pokud přidáte pomocnou metodu do třídy testu a nechcete, aby se zobrazila v **Průzkumníku testů**, nepřidávejte atribut <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> do metody.

## <a name="see-also"></a>Viz také:

- [Návod: Vývoj řízený testovacím prostředím pomocí Průzkumníka testů](quick-start-test-driven-development-with-test-explorer.md)
