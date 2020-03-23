---
title: Přečtěte si, jak otestovat kód pomocí živého testování částí
ms.date: 08/31/2017
ms.topic: conceptual
helpviewer_keywords:
- Live Unit Testing
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 748dfc592fbf7a3b9737e9f418362067b92bb8ff
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2020
ms.locfileid: "75594289"
---
# <a name="get-started-with-live-unit-testing"></a>Začínáme s funkcí Live Unit Testing

Když povolíte živé testování částí v řešení sady Visual Studio, vizuálně zobrazuje pokrytí testem a stav testů. Živé testování částí také dynamicky provádí testy při každé úpravě kódu a okamžitě vás upozorní, když vaše změny způsobí selhání testů.

Testování živých částí lze použít k testování řešení, která cílí na rozhraní .NET Framework nebo .NET Core. V tomto kurzu se naučíte používat živé testování částí vytvořením jednoduché knihovny tříd, která se zaměřuje na standard .NET, a vytvoříte projekt MSTest, který se zaměřuje na rozhraní .NET Core a otestuje ho.

Kompletní řešení Jazyka C# lze stáhnout z úložiště [MicrosoftDocs/visualstudio-docs](https://github.com/MicrosoftDocs/visualstudio-docs/tree/master/docs/test/samples/csharp/UtilityLibraries/) na GitHubu.

## <a name="prerequisites"></a>Požadavky

Tento kurz vyžaduje, abyste nainstalovali visual studio Enterprise edition s **úlohou pro vývoj napříč platformami .NET Core.**

## <a name="create-the-solution-and-the-class-library-project"></a>Vytvoření řešení a projektu knihovny tříd

Začněte vytvořením řešení Sady Visual Studio s názvem UtilityLibraries, které se skládá z jednoho projektu knihovny tříd .NET Standard, StringLibrary.

Řešení je pouze kontejner pro jeden nebo více projektů. Chcete-li vytvořit prázdné řešení, otevřete Visual Studio a postupujte takto:

1. V nabídce Visual Studio nejvyšší úrovně vyberte **Soubor** > **nového** > **projektu.**

1. Zadejte **řešení** do vyhledávacího pole šablony a pak vyberte šablonu **Prázdné řešení.**

   ::: moniker range="vs-2017"

   ![Dialogové okno **Nový projekt**](./media/lut-start/new-solution.png)

   ::: moniker-end

1. Dokončete vytváření řešení.

Teď, když jste vytvořili řešení, vytvoříte knihovnu tříd s názvem StringLibrary, která obsahuje řadu rozšiřujících metod pro práci s řetězci.

1. V **Průzkumníku řešení**klepněte pravým tlačítkem myši na řešení UtilityLibraries a vyberte **přidat** > **nový projekt**.

::: moniker range="vs-2017"

2. V dialogovém okně **Přidat nový projekt** vyberte uzel C# a pak vyberte **.NET Standard**.

   > [!NOTE]
   > Vzhledem k tomu, že naše knihovna cíle .NET Standard spíše než konkrétní implementaci .NET, může být volána z libovolné implementace rozhraní .NET, která podporuje tuto verzi .NET Standard. Další informace naleznete v tématu [.NET Standard](/dotnet/standard/net-standard).

3. V pravém podokně vyberte šablonu **Knihovna tříd (.NET Standard)** a do textového pole **Název** zadejte **StringLibrary,** jak ukazuje následující obrázek:

   ![Dialogové okno **Přidat nový projekt**](./media/lut-start/add-project-cs.png)

4. Vyberte **OK** a vytvořte projekt.

::: moniker-end

::: moniker range=">=vs-2019"

2. Zadejte **knihovnu tříd** do vyhledávacího pole šablony a vyberte šablonu **Knihovna tříd (.NET Standard).** Klikněte na **Další**.

   > [!NOTE]
   > Vzhledem k tomu, že naše knihovna cíle .NET Standard spíše než konkrétní implementaci .NET, může být volána z libovolné implementace rozhraní .NET, která podporuje tuto verzi .NET Standard. Další informace naleznete v tématu [.NET Standard](/dotnet/standard/net-standard).

3. Pojmenujte projekt **StringLibrary**.

4. Chcete-li vytvořit projekt, klepněte na **tlačítko Vytvořit.**

::: moniker-end

5. Nahraďte všechny existující kód y v okně kódu následujícím kódem:

   [!code-csharp[StringLibrary source code](samples/csharp/utilitylibraries/stringlibrary/class1.cs)]

   StringLibrary má tři statické metody:

   - `StartsWithUpper`vrátí,pokud `true` řetězec začíná velkým znakem; v opačném `false`případě vrátí .

   - `StartsWithLower`vrátí, `true` pokud řetězec začíná znakem s malou písmena; v opačném `false`případě vrátí .

   - `HasEmbeddedSpaces`vrátí,pokud `true` řetězec obsahuje vložený znak prázdného znaku; v opačném `false`případě vrátí .

6. V nabídce Visual Studia nejvyšší úrovně vyberte **Build** > **Build Solution** . Sestavení by mělo být úspěšné.

## <a name="create-the-test-project"></a>Vytvoření testovacího projektu

Dalším krokem je vytvoření projektu testování částí k testování knihovny StringLibrary. Vytvořte testy částí provedením následujících kroků:

1. V **Průzkumníku řešení**klepněte pravým tlačítkem myši na řešení UtilityLibraries a vyberte **přidat** > **nový projekt**.

::: moniker range="vs-2017"

2. V dialogovém okně **Přidat nový projekt** vyberte uzel C# a pak vyberte **.NET Core**.

   > [!NOTE]
   > Není třeba psát testy částí ve stejném jazyce jako knihovna tříd.

3. V pravém podokně vyberte šablonu **Projekt testování částí (.NET Core)** a do textového pole **Název** zadejte **StringLibraryTests,** jak ukazuje následující obrázek:

   ![Dialogové okno **Přidat nový projekt** pro projekt testování částí](./media/lut-start/add-unit-test-cs.png)

4. Vyberte **OK** a vytvořte projekt.

::: moniker-end

::: moniker range=">=vs-2019"

2. Do vyhledávacího pole šablony zadejte **test částí** a vyberte šablonu Projekt testování **částí (.NET Core).** Klikněte na **Další**.

3. Pojmenujte projekt **StringLibraryTests**.

4. Chcete-li vytvořit projekt, klepněte na **tlačítko Vytvořit.**

::: moniker-end

   > [!NOTE]
   > Tento kurz začínáme používá živé testování částí s testovacím rámcem MSTest. Můžete také použít xUnit a NUnit testovací rámce.

5. Projekt testování částí nemůže automaticky přistupovat ke knihovně tříd, kterou testuje. Testovací knihovně přístup přidáte přidáním odkazu na projekt knihovny tříd. Chcete-li to provést, `StringLibraryTests` klepněte pravým tlačítkem myši na projekt a vyberte **přidat** > **odkaz**. V dialogovém okně **Správce odkazů** zkontrolujte, zda je vybraná karta **Řešení,** a vyberte projekt StringLibrary, jak je znázorněno na následujícím obrázku.

   ![Dialogové okno **Reference Manager**](./media/lut-start/add-reference.png)

6. Vyměňte kód zkoušky často používané jednotky dodaný šablonou za následující kód:

   [!code-csharp[StringLibraryTest source code](samples/snippets/csharp/lut-start/unittest1.cs)]

7. Uložte projekt tak, že na panelu nástrojů vyberete ikonu **Uložit.**

8. Vzhledem k tomu, že kód testování částí obsahuje některé znaky, které nejsou ascii, visual studio zobrazí následující dialogové okno, které varuje, že některé znaky budou ztraceny, pokud soubor uložíte ve výchozím formátu ASCII. Zvolte tlačítko **Uložit s jiným kódováním.**

   ![Volba kódování souboru](media/lut-start/ascii-encoding.png)

9. V rozevíracím seznamu **Kódování** v dialogovém okně **Možnosti předběžného uložení** zvolte **Unicode (UTF-8 bez podpisu) – Znaková stránka 65001**, jak ukazuje následující obrázek:

   ![Výběr kódování UTF-8](media/lut-start/utf8-encoding.png)

10. Zkompilujte projekt testování částí **výběrem** > **řešení opětovného sestavení** z nabídky visual studia nejvyšší úrovně.

Vytvořili jste knihovnu tříd, stejně jako některé testy částí pro něj. Nyní jste dokončili předběžné testy potřebné k použití živého testování částí.

## <a name="enable-live-unit-testing"></a>Povolit živé testování částí

Zatím, i když jste napsali testy pro knihovnu tříd StringLibrary, jste je neprovedli. Živé testování částí je spustí automaticky, jakmile je povolíte. Chcete-li to provést, postupujte takto:

1. Volitelně vyberte okno kódu, které obsahuje kód pro StringLibrary. Toto je *buď Class1.cs* pro projekt Jazyka C# nebo *Class1.vb* pro projekt jazyka Visual Basic. (Tento krok umožňuje vizuálně zkontrolovat výsledek testů a rozsah pokrytí kódu, jakmile povolíte živé testování částí.)

1. V nabídce Visual Studio nejvyšší úrovně vyberte **Testovat** > **živé testování** > **Start** částí.

1. Visual Studio spustí live unit test, který automaticky spustí všechny testy.

Po dokončení spuštění testů **průzkumník testů** zobrazí celkové výsledky a výsledek jednotlivých testů. Kromě toho okno kódu graficky zobrazí pokrytí testovacíkód a výsledek pro testy. Jak ukazuje následující obrázek, všechny tři testy byly úspěšně provedeny. Také ukazuje, že naše testy se vztahuje `StartsWithUpper` všechny cesty kódu v metodě a tyto testy všechny úspěšně provedeny (což je označeno zelenou zaškrtnutí, "✓"). Nakonec ukazuje, že žádná z ostatních metod v StringLibrary mají pokrytí kódu (což je označeno modrou čárou "➖").

![Průzkumník testů a okno kódu po spuštění testování živé jednotky](media/lut-start/lut-results-cs.png)

Můžete také získat podrobnější informace o pokrytí testu a výsledky testů výběrem konkrétní ikonu pokrytí kódu v okně kódu. Chcete-li tento detail prozkoumat, postupujte takto:

1. Klikněte na zelenou značku zaškrtnutí na řádku, který se čte `if (String.IsNullOrWhiteSpace(s))` v metodě. `StartsWithUpper` Jak ukazuje následující obrázek, živé testování částí označuje, že tři testy pokrývají tento řádek kódu a že všechny byly úspěšně provedeny.

   ![Pokrytí kódu pro podmíněný příkaz if](media/lut-start/code-coverage-cs1.png)

1. Klikněte na zelenou značku zaškrtnutí na řádku, který se čte `return Char.IsUpper(s[0])` v metodě. `StartsWithUpper` Jak ukazuje následující obrázek, živé testování částí označuje, že pouze dva testy pokrývají tento řádek kódu a že všechny byly úspěšně provedeny.

   ![Pokrytí kódu pro příkaz return](media/lut-start/code-coverage-cs2.png)

Hlavním problémem, který identifikuje živé testování částí, je neúplné pokrytí kódu. Budete řešit v další části.

## <a name="expand-test-coverage"></a>Rozšířit pokrytí testu

V této části rozšíříte testování částí `StartsWithLower` na metodu. Během tohoto nastavení bude živé testování částí dynamicky pokračovat v testování kódu.

Chcete-li rozšířit `StartsWithLower` pokrytí kódu na metodu, postupujte takto:

1. Přidejte `TestStartsWithLower` do `TestDoesNotStartWithLower` souboru testovacího zdrojového kódu projektu následující informace a metody:

    [!code-csharp[StringLibraryTest source code](samples/snippets/csharp/lut-start/unittest2.cs#1)]

1. Upravte `DirectCallWithNullOrEmpty` metodu přidáním následujícího kódu [`Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse`](/dotnet/api/microsoft.visualstudio.testtools.unittesting.assert.isfalse) bezprostředně po volání metody.

    [!code-csharp[StringLibraryTest source code](samples/snippets/csharp/lut-start/unittest2.cs#2)]

1. Live Testování částí automaticky provede nové a upravené testy při úpravě zdrojového kódu. Jak ukazuje následující obrázek **Průzkumníka testů,** všechny testy, včetně dvou, které jste přidali, a těch, které jste upravili, byly úspěšné.

   ![Průzkumník testů po rozšíření pokrytí testu](media/lut-start/test-dynamic.png)

1. Přepněte do okna, které obsahuje zdrojový kód třídy StringLibrary. Živé testování částí nyní ukazuje, že `StartsWithLower` naše pokrytí kódu je rozšířena na metodu.

    ![Pokrytí kódu pro metodu StartsWithLower](media/lut-start/lut-extended-cs.png)

V některých případech úspěšné testy v **Průzkumníku testů** může být šedě. To znamená, že test je aktuálně spuštěna nebo že test nebyl spuštěn znovu, protože nebyly provedeny žádné změny kódu, které by měly vliv na test od jeho posledního spuštění.

Zatím všechny naše testy uspěly. V další části se podíváme, jak můžete zvládnout selhání testu.

## <a name="handle-a-test-failure"></a>Zpracování selhání testu

V této části se podíváte, jak můžete pomocí živého testování částí identifikovat, řešit potíže a řešit selhání testů. Uděláte to tak, že rozšíříte `HasEmbeddedSpaces` pokrytí testu na metodu.

1. Do testovacího souboru přidejte následující metodu:

    [!code-csharp[The TestHasEmbeddedSpaces test method](samples/snippets/csharp/lut-start/unittest2.cs#3)]

1. Při spuštění testu živé testování částí `TestHasEmbeddedSpaces` označuje, že metoda se nezdařila, jak ukazuje následující obrázek:

   ![Průzkumník testů hlásí neúspěšný test](media/lut-start/test-failure.png)

1. Vyberte okno, ve které se zobrazí kód knihovny. Živé testování částí rozšířilo `HasEmbeddedSpaces` pokrytí kódu na metodu. Také hlásí selhání testu přidáním🞩červeného " " k řádkům, na které se vztahují neúspěšné testy.

1. Najeďte přes řádek `HasEmbeddedSpaces` s podpisem metody. Živé testování částí zobrazí popisek, který hlásí, že metoda je pokryta jedním testem, jak ukazuje následující obrázek:

   ![Informace o testování živých částí v neúspěšném testu](media/lut-start/test-failure-info-cs.png)

1. Vyberte neúspěšný test **TestHasEmbeddedSpaces.** Živé testování částí poskytuje řadu možností, jako je například spuštění všech testů, spuštění vybraných testů, ladění všech testů a ladění vybraných testů, jak ukazuje následující obrázek:

   ![Možnosti testování živých částí pro neúspěšný test](media/lut-start/test-failure-options.png)

1. Chcete-li ladit neúspěšný test, vyberte **možnost Ladění vybrané.**

1. Visual Studio provede test v režimu ladění.

   Test přiřadí každý řetězec v poli `phrase` proměnné s názvem `HasEmbeddedSpaces` a předá ji metodě. Spuštění programu pozastaví a vyvolá ladicí program při `false`prvním vyhodnocení výrazu . Dialogové okno výjimky, které je [`Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue`](/dotnet/api/microsoft.visualstudio.testtools.unittesting.assert.istrue) výsledkem neočekávané hodnoty ve volání metody, je zobrazeno na následujícím obrázku.

   ![Dialogové okno Výjimka testování živých částí](media/lut-start/exception-dialog-cs.png)

   Kromě toho jsou k dispozici všechny ladicí nástroje, které sada Visual Studio poskytuje, které nám pomáhají řešit potíže s neúspěšným testem, jak ukazuje následující obrázek:

   ![Nástroje pro ladění sady Visual Studio](media/lut-start/debugging-tools-cs.png)

   Všimněte si, že v okně `phrase` **Autos,** že hodnota proměnné je "Name\tDescription", což je druhý prvek pole. Testovací metoda `HasEmbeddedSpaces` očekává, `true` že se vrátí, když je předán tento řetězec; místo toho `false`vrátí . Je zřejmé, že nerozpozná "\t", znak karty, jako vložený prostor.

1. Vyberte **Pokračovat v ladění** > **,** stiskněte **klávesu F5**nebo klepněte na tlačítko **Pokračovat** na panelu nástrojů a pokračujte ve spuštění testovacího programu. Protože došlo k neošetřené výjimce, test bude ukončen.
To poskytuje dostatek informací pro předběžné vyšetření chyby. Buď `TestHasEmbeddedSpaces` (testovací rutina) provedla `HasEmbeddedSpaces` nesprávný předpoklad nebo správně nerozpozná všechny vložené mezery.

1. Chcete-li diagnostikovat a opravit `StringLibrary.HasEmbeddedSpaces` problém, začněte s metodou. Podívejte se na `HasEmbeddedSpaces` srovnání v metodě. Předpokládá, že vložené místo je U + 0020. Standard Unicode však obsahuje řadu dalších znaků mezer. To naznačuje, že kód knihovny nesprávně testovány na znak prázdné znaky.

1. Nahraďte porovnání rovnosti voláním <xref:System.Char.IsWhiteSpace%2A?displayProperty=fullName> metody:

    [!code-csharp[The TestHasEmbeddedSpaces test method](samples/snippets/csharp/lut-start/program2.cs#1)]

1. Živé testování částí automaticky znovu spustí neúspěšnou testovací metodu a aktualizuje výsledky v okně kódu a v **Průzkumníkovi testů**, jak ukazuje následující obrázek:

    ![Úspěšný test HasEmbeddedSpaces](media/lut-start/test-success-cs.png)

## <a name="see-also"></a>Viz také

- [Živé testování částí v sadě Visual Studio](live-unit-testing.md)
- [Nejčastější dotazy k testování živých částí](live-unit-testing-faq.md)
