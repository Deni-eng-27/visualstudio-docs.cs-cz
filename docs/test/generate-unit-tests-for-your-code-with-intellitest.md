---
title: Generování testů jednotek pro kód pomocí funkce IntelliTest
ms.date: 10/05/2015
ms.prod: visual-studio-dev15
ms.topic: conceptual
f1_keywords:
- vs.UnitTest.CreateIntelliTest
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 1d7c7886e407ab7f8151ecb8f79a7eb4090aed89
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53958823"
---
# <a name="generate-unit-tests-for-your-code-with-intellitest"></a>Generování testů jednotek pro kód pomocí funkce IntelliTest

Inteligentní testování vám umožní prozkoumat kód .NET a vygenerovat testovací data a sady testování částí. Pro každý příkaz v kódu se generuje zkušební vstup, který tento příkaz spustí. Pro každou podmíněnou větev v kódu se provede Případová analýza. Například `if` kontrolní, kontrolní výrazy a všechny operace, které můžou vyvolat výjimku. Této analýzy se generují testovací data pro parametrizovaný test části metod, vytváření testů jednotek s vysokým pokrytím kódu používá.

Při spuštění IntelliTest můžete snadno zobrazit, jaké testy se nedaří a přidejte všechny nezbytné kód a opravte je. Můžete vybrat, které z vygenerované testy k uložení do testovacího projektu poskytnout sadu regrese. Po provedení změny kódu, znovu spusťte IntelliTest pro synchronizaci vygenerované testy se změnami kódu.

## <a name="availability-and-extensions"></a>Dostupnost a rozšíření

**Vytvořit IntelliTest** a **spustit inteligentní testování** příkazů nabídky:

* Jsou k dispozici v pouze Enterprise edici sady Visual Studio 2015 a novější.

* Podporuje pouze kód jazyka C#, který cílí na .NET Framework.

* Jsou [extensible](#extend-framework)a podporu generování testů MSTest, nástroji MSTest V2, NUnit, xUnit formátu.

* Nepodporuje x64 konfigurace.

## <a name="explore-use-intellitest-to-explore-your-code-and-generate-unit-tests"></a>Prozkoumejte službu: Použití IntelliTest dá prozkoumat kód a generování testů jednotek

Generování testů jednotek, vaše typy musí být veřejné. V opačném případě [vytvořit testy jednotek](#NoRun) první před jejich vytvořením.

1.  Otevřete řešení v sadě Visual Studio. Pak otevřete soubor třídy, která obsahuje metody, které chcete testovat.

2.  Klikněte pravým tlačítkem v metodě v kódu a zvolte **spustit inteligentní testování** ke generování testů jednotek pro kód v metodě.

     ![Pravé&#45;klikněte na tlačítko ve své metodě ke generování testů jednotek](../test/media/runpex.png)

     IntelliTest spustí váš kód několikrát s různými vstupy. Každé spuštění je vyjádřena v tabulka zobrazující vstupní testovací data a výsledný výstup nebo výjimky.

     ![Zobrazí se okno výsledků průzkumu s testy](../test/media/pexexplorationresults.png)

     Generování testů jednotek pro všechny veřejné metody ve třídě, jednoduše klikněte pravým tlačítkem ve třídě, nikoli konkrétní metody. Klikněte na tlačítko **spustit inteligentní testování**. Použijte rozevírací seznam v **výsledky průzkumu** okno pro zobrazení testů jednotek a vstupní data pro jednotlivé metody ve třídě.

     ![Vyberte výsledky testu, chcete-li zobrazit ze seznamu](../test/media/selectpextest.png)

     Zaznamenané výsledky ve sloupci výsledků testů, které předat, zkontrolujte, jestli odpovídat vašim očekáváním pro váš kód. Pro testy, které selžou kód podle potřeby opravte. Pak znovu spusťte IntelliTest ověření opravy.

## <a name="persist-save-the-unit-tests-as-a-regression-suite"></a>Uchování: Uložit jako sadu regresní testování částí

1.  Vyberte řádky dat, které chcete uložit s parametrizovaný test jednotek do testovacího projektu.

     ![Vyberte testy; správné&#45;klikněte a vyberte Uložit](../test/media/savepextests.png)

     Můžete zobrazit projekt testů a parametrizovaný test části, který byl vytvořen - jednotlivých částí odpovídající na jednotlivých řádcích, se ukládají do *. g.cs* soubor v projektu testu a parametrizovaný test části je uložen v odpovídající *.cs* souboru. Můžete spustit testy jednotek a zobrazit výsledky z Průzkumníka testů, stejně jako byste to udělali pro všechny testy, které jste vytvořili ručně.

     ![Soubor otevřete třídy v testovací metodě zobrazíte testu jednotek](../test/media/testmethodpex.png)

     Všechny potřebné odkazy jsou také přidány do projektu testů.

     Pokud se změní kód metody, znovu spusťte IntelliTest pro synchronizaci jednotkové testy se změnami.

## <a name="assist-use-intellitest-to-focus-code-exploration"></a>Asistent: Fokus zkoumání kódu pomocí funkce IntelliTest

1.  Pokud máte složitější kód, Intellitestu vám pomůže soustředit zkoumání kódu. Například pokud máte metodu, která má rozhraní jako parametr a existuje více než jednu třídu, která implementuje rozhraní, Intellitestu zjistí tyto třídy a zprávy upozornění.

     Zobrazování upozornění se rozhodnout, co chcete udělat.

     ![Zobrazit upozornění](../test/media/pexviewwarning.png)

2.  Po zkoumání kódu a pochopit, co chcete otestovat, můžete je vyřešit upozornění rozhodnout, které třídy k otestování rozhraní.

     ![Pravé&#45;kliknutím na upozornění a zvolte opravu](../test/media/pexfixwarning.png)

     Tato volba je přidán do *PexAssemblyInfo.cs* souboru.

     `[assembly: PexUseType(typeof(Camera))]`

3.  Teď můžete znovu spustit Intellitestu a generovat parametrizovaný test části testovací data jenom pomocí třídy, která jste opravili.

     ![Znovu spusťte IntelliTest generují testovací data](../test/media/pexwarningsfixed.png)

## <a name="specify-use-intellitest-to-validate-correctness-properties-that-you-specify-in-code"></a>Zadejte: Ověřte správnost vlastností, které zadáte v kódu pomocí funkce IntelliTest

Zadejte obecné vztah mezi vstupy a výstupy, které chcete, aby vygenerované testy jednotek pro ověření. Tato specifikace zapouzdřena v metodě, která vypadá jako testovací metody, ale univerzálně vyjadřuje. Toto je testovací metody parametrizované jednotky a pro všechny možné vstupní hodnoty, která mohou generovat IntelliTest musí obsahovat žádné kontrolní výrazy, které provedete.

##  <a name="q--a"></a>Dotazy a odpovědi

### <a name="q-can-you-use-intellitest-for-unmanaged-code"></a>DOTAZ: Můžete si IntelliTest pro nespravovaný kód?

**ODPOVĚĎ:** Ne, Intellitestu funguje jenom se spravovaným kódem.

### <a name="q-when-does-a-generated-test-pass-or-fail"></a>DOTAZ: Pokud generovaný test úspěšné nebo neúspěšné?

**ODPOVĚĎ:** Předá jako libovolné jiné jednotky testování, pokud dojde k žádné výjimky. Selže, pokud žádné kontrolní výraz selže nebo pokud testovaný kód vyvolá neošetřenou výjimku.

 Pokud máte test, který můžete předat, pokud jsou vyvolány některé výjimky, můžete nastavit jednu z následujících atributů na základě vašich požadavků na testovací metody, třídě testu nebo sestavení úrovně:

-   **PexAllowedExceptionAttribute**

-   **PexAllowedExceptionFromTypeAttribute**

-   **PexAllowedExceptionFromTypeUnderTestAttribute**

-   **PexAllowedExceptionFromAssemblyAttribute**

### <a name="q-can-i-add-assumptions-to-the-parameterized-unit-test"></a>DOTAZ: Můžete přidat předpoklady pro parametrizovaný test jednotek?

**ODPOVĚĎ:** Ano, použijte předpoklady k určení, které testovací data se nevyžaduje pro test jednotek pro konkrétní metody. Použití <xref:Microsoft.Pex.Framework.PexAssume> třídy přidat předpoklady. Můžete například přidat předpokládá, že proměnné délky není null následujícím způsobem.

 `PexAssume.IsNotNull(lengths);`

 Pokud přidáte předpokládá a znovu spusťte IntelliTest, odeberou se testovací data, která už nejsou relevantní.

### <a name="q-can-i-add-assertions-to-the-parameterized-unit-test"></a>DOTAZ: Můžete přidat kontrolní výrazy do parametrizovaný test jednotek?

**ODPOVĚĎ:** Ano, IntelliTest se zkontrolujte, že jsou uplatnění v příkazu ve skutečnosti správný při spuštění testů jednotek. Použití <xref:Microsoft.Pex.Framework.PexAssert> třídy nebo rozhraní API, která je součástí rozhraní pro testování přidat kontrolní výrazy kontrolního výrazu. Například můžete přidat kontrolní výraz, že dvě proměnné, které jsou stejné.

 `PexAssert.AreEqual(a, b);`

 Pokud chcete přidat kontrolní výraz a znovu spusťte IntelliTest, zkontroluje, že vaše kontrolní výraz je platný a test se nezdaří, pokud není.

###  <a name="NoRun"></a> DOTAZ: Můžete generovat parametrizované testy částí bez nutnosti nejprve spuštění IntelliTest?

**ODPOVĚĎ:** Ano, klikněte pravým tlačítkem na třídy nebo metody, a pak zvolte **vytvořit IntelliTest**.

 ![Pravé&#45;klikněte na tlačítko editoru, zvolte možnost vytvořit IntelliTest](../test/media/pexcreateintellitest.png)

 Přijměte výchozí formát vygenerovat vaše testy nebo změnit, jak se s názvem projektu a testy. Můžete vytvořit nový testovací projekt nebo uložit do existujícího projektu testů.

 ![Vytvoření IntelliTest se výchozí MSTest](../test/media/pexcreateintellitestmstest.png)

<a name="extend-framework"></a>
### <a name="q-can-i-use-other-unit-test-frameworks-with-intellitest"></a>DOTAZ: Můžete použít jiné rozhraní pro testování částí pomocí funkce IntelliTest

**ODPOVĚĎ:** Ano, postupujte podle těchto kroků [najít a nainstalovat jiná rozhraní Framework](../test/install-third-party-unit-test-frameworks.md).
Testovací rozhraní framework rozšíření jsou k dispozici také v aplikaci Visual Studio Marketplace:

* [NUnit rozšíření pro generátory testu](https://marketplace.visualstudio.com/items?itemName=NUnitDevelopers.TestGeneratorNUnitextension-18371)
* [rozšíření xUnit.net pro generátory testu](https://marketplace.visualstudio.com/items?itemName=BradWilson.xUnitnetTestExtensions)


Po restartování sady Visual Studio a znovu otevřete řešení, klikněte pravým tlačítkem na třídy nebo metody a pak zvolte **vytvořit IntelliTest**. Vyberte nainstalované rozhraní tady:

![Vyberte jiné rámce jednotkových testů pro IntelliTest](../test/media/pexcreateintellitestextensions.png)

Potom spusťte IntelliTest generování testů jednotek v jejich odpovídající *. g.cs* soubory.


### <a name="q-can-i-learn-more-about-how-the-tests-are-generated"></a>DOTAZ: Dozvím víc o tom, jak jsou generovány testy?

**ODPOVĚĎ:** Ano, chcete-li získat základní přehled, přečtěte si tento [blogový příspěvek](https://blogs.msdn.microsoft.com/devops/2015/07/05/intellitest-one-test-to-rule-them-all/).
