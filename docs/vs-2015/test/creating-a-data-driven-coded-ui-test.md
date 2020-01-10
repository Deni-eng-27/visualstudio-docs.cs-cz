---
title: Vytvoření programového testu uživatelského rozhraní řízeného daty | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-test
ms.topic: conceptual
helpviewer_keywords:
- coded UI tests, data-driven
ms.assetid: 5838f02d-001f-49ce-adce-c9ea1afaec2f
caps.latest.revision: 58
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 1db35e1eb98ad23a4414a48389092a3b05485527
ms.sourcegitcommit: c150d0be93b6f7ccbe9625b41a437541502560f5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2020
ms.locfileid: "75851855"
---
# <a name="creating-a-data-driven-coded-ui-test"></a>Vytvoření datově řízeného programového testu UI
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

K testování různých podmínek, můžete spustit testy několikrát s různými hodnotami parametrů. S daty kódované UI testy jsou pohodlný způsob, jak to provést. Můžete definovat hodnoty parametrů ve zdroji dat a každý řádek ve zdroji dat je iteraci programový test uživatelského rozhraní. Celkový výsledek testu budou založeny na výsledek pro všechny iterace. Například pokud jedna iteraci testu nezdaří, celkový výsledek testu je selhání.

 **Požadavky**

- Visual Studio Enterprise

## <a name="create-a-data-driven-coded-ui-test"></a>Vytvoření datově řízeného programového testu UI
 Tato ukázka vytvoří programový test uživatelského rozhraní, která běží na Windows Kalkulačka aplikace. Sečte dvě čísla a používá kontrolní výraz k ověření, že součet je správný. Dále je kontrolní výraz a hodnoty parametrů pro dvě čísla kódovány tak, aby se staly řízenými daty a uloženy v souboru hodnot oddělených čárkami (. csv).

#### <a name="step-1---create-a-coded-ui-test"></a>Krok 1: vytvoření programového testu uživatelského rozhraní

1. Vytvoření projektu.

     ![Vytvoření projektu programového testu uživatelského rozhraní](../test/media/cuit-datadriven.png "CUIT_dataDriven_")

2. Vyberte, chcete-li zaznamenávat akce.

     ![Vyberte, chcete-li zaznamenávat akce](../test/media/cuit-datadriven-generatecodedialog.png "CUIT_dataDriven_GenerateCodeDialog")

3. Otevřete aplikaci kalkulačky a spusťte záznam testu.

     ![Zaznamenat akce](../test/media/cuit-datadriven-cuitbuilder.png "CUIT_dataDriven_CUITBuilder")

4. Přidat 1 a 2, pozastavit záznam a generovat zkušební metody. Později nahradíme hodnoty tohoto uživatelského vstupu hodnotami z datového souboru.

     ![Generovat testovací metodu](../test/media/cuit-datadriven-cuitbuildergencode.png "CUIT_dataDriven_CUITBuilderGenCode")

     Zavřete Tvůrce testu. Metoda je přidána do testu:

    ```csharp
    [TestMethod]
    public void CodedUITestMethod1()
    {
        // To generate code for this test, select "Generate Code for Coded UI Test" from the shortcut menu and select one of the menu items.
        this.UIMap.AddNumbers();

    }
    ```

5. Použití `AddNumbers()` metodu k ověření, že test běží. Umístěte kurzor na slovo v testovací metodě uvedené výše, otevřete kontextovou nabídku a zvolte **spustit testy**. (Klávesová zkratka: CTRL + R, T).

     Výsledek testu, který ukazuje, zda byl test úspěšný nebo neúspěšný, se zobrazí v okně Průzkumník testů. Chcete-li otevřít okno Průzkumník testů, v nabídce **test** zvolte možnost **okna** a pak zvolte možnost **Průzkumník testů**.

6. Vzhledem k tomu, že zdroj dat je možné použít také pro hodnoty parametru kontrolního výrazu, které jsou používány testem k ověření očekávaných hodnot – přidáváme kontrolní výraz pro ověření, že součet dvou čísel je správný. Umístěte kurzor na slovo v testovací metodě uvedené výše, otevřete kontextovou nabídku a zvolte **generovat kód pro programový Test uživatelského rozhraní**a potom **použití Tvůrce programového testu UI**.

     Mapování ovládacího prvku text v kalkulačce zobrazující součet.

     ![Mapování ovládacího prvku text uživatelského rozhraní](../test/media/cuit-datadriven-addassertion.png "CUIT_dataDriven_AddAssertion")

7. Přidáte kontrolní výraz, který ověří správnost hodnotu Součet. Zvolte **ZobrazenýText** vlastnost, která má hodnotu **3** a klikněte na tlačítko **přidat kontrolní výraz**. Použití **AreEqual** Komparátor a ověřte, zda je hodnota porovnání **3**.

     ![Konfigurace kontrolního výrazu](../test/media/cuit-datadriven-builderaddassertion2.png "CUIT_dataDriven_BuilderAddAssertion2")

8. Po dokončení konfigurace kontrolního výrazu, generování kódu z Tvůrce znovu. Tím se vytvoří novou metodu pro ověření.

     ![Generování metody kontrolního výrazu](../test/media/cuit-datadriven-assertiongencode.png "CUIT_dataDriven_AssertionGenCode")

     Protože `ValidateSum` metoda ověří výsledky `AddNumbers` metoda, jej přesunout na konec bloku kódu.

    ```csharp
    public void CodedUITestMethod1()
    {

        // To generate code for this test, select "Generate Code for Coded UI Test" from the shortcut menu and select one of the menu items.
        this.UIMap.AddNumbers();
        this.UIMap.ValidateSum();

    }
    ```

9. Ověřte, že test běží za použití `ValidateSum()` metody. Umístěte kurzor na slovo v testovací metodě uvedené výše, otevřete kontextovou nabídku a zvolte **spustit testy**. (Klávesová zkratka: CTRL + R, T).

     V tomto okamžiku všechny hodnoty parametrů jsou definovány v jejich metod jako konstanty. Teď vytvoříme datovou sadu, která bude mít na test řízená data.

#### <a name="step-2---create-a-data-set"></a>Krok 2: vytvoření datové sady

1. Přidejte textový soubor do projektu dataDrivenSample s názvem `data.csv`.

     ![Přidat do projektu soubor hodnot oddělených čárkou](../test/media/cuit-datadriven-addcsvfile.png "CUIT_dataDriven_AddCSVFile")

2. Naplňte soubor. csv následujícími daty:

    |Num1|Num2|Sum|
    |----------|----------|---------|
    |3|4|7|
    |5|6|11|
    |6|8|14|

     Po přidání data, soubor by měl vypadat takto:

     ![Naplňte. Soubor CSV s daty](../test/media/cuit-datadriven-adddatatocsvfile.png "CUIT_dataDriven_AddDataToCSVFile")

3. Je důležité uložit soubor. csv pomocí správného kódování. V nabídce **soubor** vyberte možnost **Upřesnit možnosti uložení** a jako kódování vyberte **Unicode (UTF-8 bez signatur) – codepage 65001** .

4. Soubor. CSV musí být zkopírován do výstupního adresáře nebo nelze spustit test. Ke zkopírování použijte okno Vlastnosti.

     ![Nasaďte. Soubor CSV](../test/media/cuit-datadriven-deploycsvfile.png "CUIT_dataDriven_DeployCSVFile")

     Teď, když máme datovou sadu vytvořenou, můžeme navazovat data na test.

#### <a name="step-3--add-data-source-binding"></a>Krok 3 – přidání vazby zdroje dat

1. K vytvoření vazby zdroje dat, přidejte `DataSource` atribut do existujícího `[TestMethod]` atribut, který je hned nad testovací metody.

    ```
    [DataSource("Microsoft.VisualStudio.TestTools.DataSource.CSV", "|DataDirectory|\\data.csv", "data#csv", DataAccessMethod.Sequential), DeploymentItem("data.csv"), TestMethod]
    public void CodedUITestMethod1()
    {

        // To generate code for this test, select "Generate Code for Coded UI Test" from the shortcut menu and select one of the menu items.
        this.UIMap.AddNumbers();
        this.UIMap.ValidateSum();

    }

    ```

     Zdroj dat je teď k dispozici pro použití v této zkušební metodě.

    > [!TIP]
    > Zobrazit [ukázky atribut zdroje dat](#CreateDataDrivenCUIT_QA_DataSourceAttributes) v Q & části ukázky použití jiných typů zdrojů dat, jako jsou XML, SQL Express a Excel.

2. Spusťte test.

     Všimněte si, že test běží až tři iterace. Je to proto tří řádků dat obsahuje zdroj dat, která byla vázána. Ale také si povšimněte, že test se pořád používá hodnoty parametrů konstantní a přidává 1 + 2 s součet 3 pokaždé, když.

     Dále nakonfigurujeme test tak, aby používal hodnoty v souboru zdroje dat.

#### <a name="step-4--use-the-data-in-the-coded-ui-test"></a>Krok 4 – použití dat v programovém testu UI

1. Do horní části souboru CodedUITest.cs přidejte `using Microsoft.VisualStudio.TestTools.UITesting.WinControls`:

    ```
    using System;
    using System.Collections.Generic;
    using System.Text.RegularExpressions;
    using System.Windows.Input;
    using System.Windows.Forms;
    using System.Drawing;
    using Microsoft.VisualStudio.TestTools.UITesting;
    using Microsoft.VisualStudio.TestTools.UnitTesting;
    using Microsoft.VisualStudio.TestTools.UITest.Extension;
    using Keyboard = Microsoft.VisualStudio.TestTools.UITesting.Keyboard;
    using Microsoft.VisualStudio.TestTools.UITesting.WinControls;
    ```

2. Přidat `TestContext.DataRow[]` v `CodedUITestMethod1()` metodu, která použije hodnoty ze zdroje dat. Hodnoty zdroje dat přepsat konstanty přiřazené k ovládacím prvkům UIMap pomocí ovládacích prvků `SearchProperties`:

    ```
    public void CodedUITestMethod1()
    {

        // To generate code for this test, select "Generate Code for Coded UI Test" from the shortcut menu and select one of the menu items.
        this.UIMap.UICalculatorWindow.UIItemWindow.UIItem1Button.SearchProperties[WinButton.PropertyNames.Name] = TestContext.DataRow["Num1"].ToString();this.UIMap.UICalculatorWindow.UIItemWindow21.UIItem2Button.SearchProperties[WinButton.PropertyNames.Name] = TestContext.DataRow["Num2"].ToString();
        this.UIMap.AddNumbers();
        this.UIMap.ValidateSumExpectedValues.UIItem2TextDisplayText = TestContext.DataRow["Sum"].ToString();
        this.UIMap.ValidateSum();

    }
    ```

     Chcete-li zjistit vlastnosti vyhledávání, které chcete data na kódu, použijte Editor programového testu uživatelského rozhraní.

    - Otevřete soubor UIMap. UITest.

         ![Otevřít Editor programového testu UI](../test/media/cuit-datadriven-opentesteditor.png "CUIT_dataDriven_OpenTestEditor")

    - Zvolte akce uživatelského rozhraní a sledovat odpovídající mapování ovládacích prvků uživatelského rozhraní. Všimněte si, jak mapování odpovídá kódu, například `this.UIMap.UICalculatorWindow.UIItemWindow.UIItem1Button`.

         ![Použití editoru programového testu UI pro pomoc s kódem](../test/media/cuit-datadriven-testeditor.png "CUIT_dataDriven_TestEditor")

    - V okně Vlastnosti otevřete **Vlastnosti hledání**. Vlastnosti hledání **název** co je právě zpracováván v kódu pomocí zdroje dat je hodnota. Například `SearchProperties` jsou přiřazeny hodnoty v prvním sloupci každý řádek dat: `UIItem1Button.SearchProperties[WinButton.PropertyNames.Name] = TestContext.DataRow["Num1"].ToString();`. Pro tři iterace, tento test změní **název** hodnotu pro vlastnost vyhledávání na 3, pak 5 a nakonec 6.

         ![Použití vlastností hledání k usnadnění při kódování](../test/media/cuit-datadriven-searchproperties.png "CUIT_dataDriven_SearchProperties")

3. Uložte řešení.

#### <a name="step-5--run-the-data-driven-test"></a>Krok 5 – spuštění testu řízeného daty

1. Ověřte, že test nyní řízené daty opětovným spuštěním testu.

    Měli byste vidět testovací běh prostřednictvím tří iterací pomocí hodnot v souboru. csv. Ověření by měl pracovat tak dobře, a zobrazit testu jako úspěšný v aplikaci Test Explorer.

   **Pokyny**

   Další informace naleznete v tématu [testování pro průběžné doručování pomocí sady Visual studio 2012 – Kapitola 2: testování částí: testování vnitřních](https://msdn.microsoft.com/library/jj159340.aspx) a [testování pro průběžné doručování pomocí sady Visual Studio 2012 – Kapitola 5: automatizace systémových testů](https://msdn.microsoft.com/library/jj159335.aspx)

## <a name="q--a"></a>Dotazy a odpovědi

### <a name="CreateDataDrivenCUIT_QA_DataSourceAttributes"></a> Co jsou atributy zdroje dat pro další typy zdrojů dat, jako je například SQL Express nebo XML?
 Ukázka řetězce zdrojů dat v následující tabulce můžete použít zkopírováním do vašeho kódu a provedením nezbytných úpravách.

 **Typy zdrojů dat a atributy**

- CSV

     `[DataSource("Microsoft.VisualStudio.TestTools.DataSource.CSV", "|DataDirectory|\\data.csv", "data#csv", DataAccessMethod.Sequential), DeploymentItem("data.csv"), TestMethod]`

- Excel

     `DataSource("System.Data.Odbc", "Dsn=ExcelFiles;Driver={Microsoft Excel Driver (*.xls)};dbq=|DataDirectory|\\Data.xls;defaultdir=.;driverid=790;maxbuffersize=2048;pagetimeout=5;readonly=true", "Sheet1$", DataAccessMethod.Sequential), DeploymentItem("Sheet1.xls"), TestMethod]`

- Testovací případ v Team Foundation Server

     `[DataSource("Microsoft.VisualStudio.TestTools.DataSource.TestCase", "http://vlm13261329:8080/tfs/DefaultCollection;Agile", "30", DataAccessMethod.Sequential), TestMethod]`

- XML

     `[DataSource("Microsoft.VisualStudio.TestTools.DataSource.XML", "|DataDirectory|\\data.xml", "Iterations", DataAccessMethod.Sequential), DeploymentItem("data.xml"), TestMethod]`

- SQL Express

     `[DataSource("System.Data.SqlClient", "Data Source=.\\sqlexpress;Initial Catalog=tempdb;Integrated Security=True", "Data", DataAccessMethod.Sequential), TestMethod]`

### <a name="q-can-i-use-data-driven-tests-on-my-windows-phone-app"></a>Otázka: mohu na aplikaci Windows Phone použít testy řízené daty?
 **Odpověď:** Ano. Programové testy UI založené na datech pro Windows Phone jsou definovány pomocí atributu DataRow v testovací metodě. V následujícím příkladu x a y používají hodnoty 1 a 2 pro první iteraci a-1 a-2 pro druhou iteraci testu.

```
[DataRow(1, 2, DisplayName = "Add positive numbers")]
[DataRow(-1, -2, DisplayName = "Add negative numbers")]
[TestMethod]
public void DataDrivingDemo_MyTestMethod(int x, int y)

```

### <a name="q-why-cant-i-modify-the-code-in-the-uimapdesigner-file"></a>Otázka: Proč nemůžu změnit kód v souboru UIMap. Designer?
 **A:** Všechny změny kódu, které provedete v souboru UIMapDesigner.cs, budou přepsány pokaždé, když generujete kód pomocí Tvůrce programového testu uživatelského rozhraní UIMap. V této ukázce a ve většině případů změny kódu potřebné k povolení testu použít zdroj dat lze provést v souboru zdrojového kódu testu (tj. CodedUITest1.cs).

 Pokud je třeba změnit zaznamenanou metodu, musíte ji zkopírovat do souboru UIMap.cs a přejmenovat ji. Soubor UIMap.cs lze použít k přepsání metod a vlastností v souboru UIMapDesigner.cs. Je třeba odebrat odkaz na původní metodu v kódovaném souboru UITest.cs a nahradit ji názvem přejmenované metody.

## <a name="see-also"></a>Viz také:

- [UIMap](/previous-versions/dd580454(v=vs.140))
- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert>
- [Použití automatizace uživatelského rozhraní k testování kódu](../test/use-ui-automation-to-test-your-code.md)
- [Vytváření programových testů uživatelského rozhraní](../test/use-ui-automation-to-test-your-code.md#VerifyingCodeUsingCUITCreate)
- [Doporučené postupy pro programové testy UI](../test/best-practices-for-coded-ui-tests.md)
- [Podporované konfigurace a platformy pro programové testy uživatelského rozhraní a zaznamenávání akcí](../test/supported-configurations-and-platforms-for-coded-ui-tests-and-action-recordings.md)
