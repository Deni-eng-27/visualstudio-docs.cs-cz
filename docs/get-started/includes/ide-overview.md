---
ms.date: 03/19/2019
ms.technology: vs-ide-general
ms.custom: vs-get-started
ms.author: gewarren
author: gewarren
manager: jillfra
ms.topic: include
ms.openlocfilehash: c411df964d0f0ffb6a96484f6ad4d245d561410c
ms.sourcegitcommit: 4ffb7be5384ad566ce46538032bf8561754c61a4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/15/2019
ms.locfileid: "58070331"
---
Visual Studio *integrovaného vývojového prostředí* je creative odrazový, můžete použít k úpravám, ladit a sestavovat kód a pak publikujete aplikaci. Integrované vývojové prostředí (IDE) je plně funkční program, který lze použít pro mnoho aspektů vývoje softwaru. Kromě standardní editor a ladicího programu, že většina integrovanými vývojovými prostředími poskytnout, Visual Studio obsahuje kompilátory, nástroje dokončování kódu, grafičtí návrháři pro a mnoho dalších funkcí, které usnadňují proces vývoje softwaru.

::: moniker range="vs-2017"

![Integrované vývojové prostředí Visual Studio 2017](../media/visual-studio-ide.png)

::: moniker-end

::: moniker range="vs-2019"

[![](../media/vs-2019/ide-overview.png "Prostředí IDE sady Visual Studio")](../media/vs-2019/ide-overview.png#lightbox)

::: moniker-end

Tento obrázek ukazuje sady Visual Studio s otevřít projekt a několika okny nástrojů klíče, které budete pravděpodobně používat:

- [Průzkumník řešení](../../ide/solutions-and-projects-in-visual-studio.md) (vpravo nahoře) umožňuje zobrazit, přejděte a spravovat soubory kódu. **Průzkumník řešení** pomáhá organizovat kód seskupením soubory do [řešení a projekty](../tutorial-projects-solutions.md).

- [Okno editoru](../../ide/writing-code-in-the-code-and-text-editor.md) (System center), kde budete pravděpodobně tráví většinu svého času zobrazí obsah souboru. Toto je, kde můžete upravit kódu nebo navrhnout uživatelské rozhraní, jako je například okno s tlačítka a textová pole.

::: moniker range="vs-2017"

- [Okno výstup](../../ide/reference/output-window.md) (dole uprostřed) je, kde sada Visual Studio odešle oznámení, jako jsou ladění a chybové zprávy, upozornění kompilátoru, publikování stavové zprávy a další. Každý zdroj zprávy má svůj vlastní kartu.

::: moniker-end

- [Team Explorer](/azure/devops/user-guide/work-team-explorer?view=vsts) (vpravo dole) umožňuje sledování pracovních položek a sdílet s ostatními kód pomocí technologie pro řízení verze, například [Git](https://git-scm.com/) a [Team Foundation verze ovládacího prvku (TFVC)](/azure/devops/repos/tfvc/overview?view=vsts).

## <a name="editions"></a>Edice

::: moniker range="vs-2017"

Visual Studio je k dispozici pro Windows a Mac. [Visual Studio pro Mac](/visualstudio/mac/) má mnoho stejných funkcí jako Visual Studio 2017 a je optimalizovaná pro vývoj multiplatformní a mobilní aplikace. Tento článek se týká Windows verze sady Visual Studio 2017.

Existují 3 edicích sady Visual Studio 2017: Community, Professional a Enterprise. V tématu [porovnání Visual Studio 2017 integrovanými vývojovými prostředími](https://visualstudio.microsoft.com/vs/compare/) Další informace o funkcích, které jsou podporované v každé edici.

::: moniker-end

::: moniker range="vs-2019"

Visual Studio je k dispozici pro Windows a Mac. [Visual Studio pro Mac](/visualstudio/mac/) má mnoho stejných funkcí jako Visual Studio 2019 a je optimalizovaná pro vývoj multiplatformní a mobilní aplikace. Tento článek se zaměřuje na verzi Windows. 2019 Visual Studio.

Existují tři edice sady Visual Studio 2019: Community, Professional a Enterprise. Zobrazit [porovnání prostředí IDE Visual Studio](https://visualstudio.microsoft.com/vs/compare/) Další informace o funkcích, které jsou podporované v každé edici.

::: moniker-end

## <a name="popular-productivity-features"></a>Oblíbené pro zvýšení produktivity

Mezi oblíbené funkce v sadě Visual Studio, které vám umožní být produktivnější při vývoji softwaru, patří:

- Podtržení vlnovkou a [rychlé akce](../../ide/quick-actions.md)

   Podtržení vlnovkou jsou podtržení vlnovkou, které vás upozorní na chyby nebo potenciální problémy v kódu při psaní. Tyto vizuální záchytné body umožňují opravit problémy okamžitě bez čekání na chyby mají být zjišťované, a během sestavování nebo při spuštění programu. Pokud najedete myší vlnovka, zobrazí se další informace o této chybě. Žárovky může také zobrazit na levém okraji s akcemi, známé jako rychlých akcí, chcete-li vyřešit chybu.

   ![Podtržení vlnovkou v sadě Visual Studio](../media/squiggles-error.png)

::: moniker range=">=vs-2019"

- Kód čištění

   Kliknutím na tlačítko, formátování kódu a použít libovolný kód opravy navrhl vaše [nastavení stylu kódu](../../ide/reference/options-text-editor-csharp-formatting.md), [.editorconfig konvence](../../ide/create-portable-custom-editor-options.md), a [analyzátory Roslyn](../../code-quality/roslyn-analyzers-overview.md). **Kód čištění** pomáhá při řešení problémů ve vašem kódu, než se přejde k revizi kódu. (Aktuálně k dispozici pro C# pouze kód.)

   ![Tlačítko Vyčištění kódu v sadě Visual Studio](../media/vs-2019/code-cleanup.png)

::: moniker-end

- [Refactoring](../../ide/refactoring-in-visual-studio.md)

   Refaktoring zahrnuje operace, jako jsou inteligentní přejmenováním proměnné, extrahování jeden nebo více řádků kódu do nové metody, změna pořadí parametrů metod a dalších.

   ![Refaktoring v sadě Visual Studio](../media/refactoring-menu.png)

- [IntelliSense](../../ide/using-intellisense.md)

   Technologie IntelliSense je termín pro sadu funkcí, která zobrazí informace o kódu přímo v editoru a v některých případech může zapisovat malé části kódu za vás. Je to jako mít základní dokumentaci vložené v editoru, což vám ušetří nebudou muset vyhledat informace o typu jinde. Funkce technologie IntelliSense se liší podle jazyka. Další informace najdete v tématu [jazyka C# IntelliSense](../../ide/visual-csharp-intellisense.md), [Visual C++ IntelliSense](../../ide/visual-cpp-intellisense.md), [technologie IntelliSense jazyka JavaScript](../../ide/javascript-intellisense.md), a [jazyka Visual Basic IntelliSense](../../ide/visual-basic-specific-intellisense.md). Následující obrázek znázorňuje, jak technologie IntelliSense zobrazí seznam členů pro typ:

   ![Seznam členů sady Visual Studio](../media/intellisense-list-members.png)

- [Snadné spuštění](../../ide/reference/quick-launch-environment-options-dialog-box.md)

   Visual Studio, může to působit příliš složitě čas od času s tolika nabídky, možnosti a vlastnosti. **Snadné spuštění** vyhledávacího pole je skvělý způsob, jak rychle najít, co potřebujete, v sadě Visual Studio. Když začnete psát název něco, co hledáte, Visual Studio obsahuje výsledky, které dostanete, přesně, kde potřebujete přejít. Pokud chcete přidat funkce do sady Visual Studio, například pro přidání podpory pro další programovací jazyk, **Snadné spuštění** poskytuje výsledky, které otevřete instalační program sady Visual Studio k instalaci úloh nebo jednotlivých komponent.

   > [!TIP]
   > Stisknutím klávesy **Ctrl**+**Q** jako zástupce **Snadné spuštění** vyhledávacího pole.

   ::: moniker range="vs-2017"

   ![Rychlé spuštění vyhledávacího pole v sadě Visual Studio 2017](../media/quick-launch-nuget.png)

   ::: moniker-end

   ::: moniker range="vs-2019"

   ![Rychlé spuštění vyhledávacího pole v aplikaci Visual Studio 2019](../media/vs-2019/quick-launch-nuget.png)

   ::: moniker-end

- [Live sdílené složky](/visualstudio/liveshare/)

   Společně editujte a laďte s ostatními v reálném čase, bez ohledu na to, co váš typ aplikace nebo programovací jazyk. Můžete okamžitě a bezpečně sdílet svůj projekt a podle potřeby, ladicími relacemi, terminálu instance místního hostitele webové aplikace, hlasových hovorů a další.

- [Hierarchie volání](../../ide/reference/call-hierarchy.md)

   **Hierarchie volání** okno zobrazuje metody, které volají vybrané metody. To může být užitečné informace, pokud uvažujete o změně nebo odebrání metodu, nebo když se snažíte vysledování chybu.

   ![Hierarchie volání – okno](../../ide/reference/media/call-hierarchy-csharp-expanded.png)

- [CodeLens](../../ide/find-code-changes-and-other-history-with-codelens.md)

   CodeLens vám pomůže najít odkazy na kód, změny kódu, propojené chyby, pracovní položky, revize kódu a testy jednotek, to vše bez opuštění editoru.

   ![Funkce CodeLens](../media/codelens-overview.png)

- [Přejít k definici](../../ide/go-to-and-peek-definition.md)

   Funkce Přejít k definici přejdete přímo do umístění, kde je funkce nebo typ definován.

   ![Přejít k definici](../media/go-to-definition-menu.png)

- [Náhled definice](../../ide/how-to-view-and-edit-code-by-using-peek-definition-alt-plus-f12.md)

   **Definice operace Peek** okno zobrazuje definici metody nebo typ bez nutnosti otevřít ve skutečnosti samostatný soubor.

   ![Náhled definice](../media/peek-definition.png)

## <a name="install-the-visual-studio-ide"></a>Instalace sady Visual Studio IDE

V této části vytvoříte jednoduchý projekt vyzkoušet si některé z akcí, které vám pomůžou s Visual Studio. Budete používat [IntelliSense](../../ide/using-intellisense.md) jako kódování podpory, ladit aplikaci a zobrazit tak hodnotu proměnné během provádění programu a Změna barevného motivu.

::: moniker range="vs-2017"

Abyste mohli začít, [stáhněte si Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) a nainstalovat do vašeho systému. Modulární instalačního programu umožňuje vybrat a nainstalovat *úlohy*, což jsou skupiny funkce potřebné pro programovací jazyk nebo platformu dáváte přednost. Postupovat podle kroků pro [vytvoření programu](#create-a-program), je nutné vybrat **vývoj pro různé platformy .NET Core** úloh během instalace.

::: moniker-end

::: moniker range=">=vs-2019"

Abyste mohli začít, [stáhněte si Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) a nainstalovat do vašeho systému. Modulární instalačního programu umožňuje vybrat a nainstalovat *úlohy*, což jsou skupiny funkce potřebné pro programovací jazyk nebo platformu dáváte přednost. Postupovat podle kroků pro [vytvoření programu](#create-a-program), je nutné vybrat **vývoj pro různé platformy .NET Core** úloh během instalace.

::: moniker-end

![Úlohy pro vývoj pro různé platformy .NET core v instalační program sady Visual Studio](../media/dotnet-core-cross-platform-workload.png)

Když poprvé otevřete Visual Studio, můžete volitelně [přihlášení](../../ide/signing-in-to-visual-studio.md) pomocí účtu Microsoft nebo pracovní nebo školní účet.

## <a name="create-a-program"></a>Vytvoření programu

Pojďme začít a vytvořit jednoduchý program.

::: moniker range="vs-2017"

1. Otevřít Visual Studio.

1. V panelu nabídky zvolte **souboru** > **nový** > **projektu**.

   ![Soubor > Nový projekt v řádku nabídek](../media/file-new-project-menu.png)

   **Nový projekt** dialogové okno zobrazí několik projektů *šablony*. Šablona obsahuje základní souborů a nastavení potřebných pro typ daného projektu.

1. Zvolte **.NET Core** šablony kategorie v části **Visual C#** a klikněte na tlačítko **Konzolová aplikace (.NET Core)** šablony. V **název** textového pole, typ **HelloWorld**a pak vyberte **OK** tlačítko.

   ![Šablona aplikace .NET core](../media/overview-new-project-dialog.png)

   > [!NOTE]
   > Pokud se nezobrazí **.NET Core** kategorie, je nutné nainstalovat **vývoj pro různé platformy .NET Core** pracovního vytížení. Chcete-li to provést, zvolte **otevřít instalační program Visual Studio** odkaz v levé dolní části **nový projekt** dialogového okna. Jakmile se instalační program sady Visual Studio otevře, posuňte se dolů a vyberte **vývoj pro různé platformy .NET Core** úlohy a pak vyberte **změnit**.

   Visual Studio vytvoří projekt. To je jednoduchá aplikace "Hello World", která volá <xref:System.Console.WriteLine?displayProperty=nameWithType> metodu pro zobrazení řetězcový literál "Hello World!" v okně konzoly (výstup programu).

   Po chvíli, by měl vypadat přibližně takto:

   ![Visual Studio – sada IDE](../media/overview-ide-console-app.png)

   Kód jazyka C# pro vaši aplikaci se zobrazí v okně editoru, což zabírá většinu prostoru. Všimněte si, že text je automaticky barevně zvýrazněné k označení různých částí kódu, jako jsou klíčová slova a typy. Kromě toho malé, svislé přerušované čáry v kódu označují, které složené závorky odpovídat mezi sebou a čísla řádků vám pomohou vyhledat kód později. Můžete také malé, zabalený mínus bloky kódu rozbalíte nebo sbalíte. Tento kód funkce osnovy vám umožňuje skrýt kód, který už nebudete potřebovat, a usnadnit tak minimalizovat zbytečné soubory na obrazovce. Soubory projektu jsou uvedeny na pravé straně v okně **Průzkumníka řešení**.

   ![Visual Studio integrované vývojové prostředí s červená pole](../media/overview-ide-console-app-red-boxes.png)

   K dispozici další nabídky a panely nástrojů, ale teď přejdeme teď.

1. Nyní spusťte aplikaci. To lze provést výběrem **spustit bez ladění** z **ladění** nabídky na řádku nabídek. Můžete také stisknout klávesu **Ctrl**+**F5**.

   ![Ladit > Spustit bez ladění nabídky](../media/overview-start-without-debugging.png)

   Visual Studio vytvoří aplikaci a otevře se okno konzoly se zprávou **Hello World!**. Nyní máte funkční aplikaci.

   ![Okno konzoly](../media/overview-console-window.png)

1. Zavřete okno konzoly stisknutím libovolné klávesy na klávesnici.

1. Přidejme do aplikace další kód. Přidejte následující kód jazyka C# před řádek, který říká `Console.WriteLine("Hello World!");`:

   ```csharp
   Console.WriteLine("\nWhat is your name?");
   var name = Console.ReadLine();
   ```

   Tento kód zobrazí **jak se jmenuješ?** v okně konzoly a potom počká, dokud uživatel zadá nějaký text, za nímž následuje **Enter** klíč.

1. Změňte řádek, který říká `Console.WriteLine("Hello World!");` v následujícím kódu:

   ```csharp
   Console.WriteLine($"\nHello {name}!");
   ```

1. Znovu spusťte aplikaci tak, že vyberete **ladění** > **spustit bez ladění** nebo stisknutím klávesy **Ctrl**+**F5**.

   Visual Studio znovu sestaví aplikaci a otevře se okno konzoly a vás vyzve k zadání název vaší.

1. Zadejte název v okně konzoly a stisknutím klávesy **Enter**.

   ![Vstup okno konzoly](../media/overview-console-input.png)

1. Stisknutím jakékoli klávesy zavřete okno konzoly a zastavit spuštěný program.

::: moniker-end

::: moniker range=">=vs-2019"

1. Otevřít Visual Studio.

   Úvodní okno s různými možnostmi pro klonování úložiště, poslední projekt otevřením nebo vytvořením zcela nový projekt.

1. Zvolte **vytvořte nový projekt**.

   ![Visual Studio spustit okno Vytvoření nového projektu](../media/vs-2019/start-window-create-new-project.png)

   **Vytvořte nový projekt** okno otevře a zobrazí několik projektů *šablony*. Šablona obsahuje základní souborů a nastavení potřebných pro typ daného projektu.

1. Chcete-li najít šablonu jsme mají, zadejte nebo zadejte **konzoly .net core** do vyhledávacího pole. Seznam dostupných šablon se automaticky filtruje podle klíčových slov, které jste zadali. Výsledky šablony můžete dále filtrovat výběrem **C#** z **jazyk** rozevíracího seznamu. Vyberte **Konzolová aplikace (.NET Core)** šablony a klikněte na tlačítko **Další**.

    ![Vytvoření nového projektu v sadě Visual Studio](../media/vs-2019/create-new-project.png)

1. V **konfigurovat nový projekt** okno, zadejte **HelloWorld** v **název projektu** pole, Volitelně můžete změnit umístění adresáře pro soubory projektu a pak Zvolte **vytvořit**.

   ![Konfigurovat nový projekt v sadě Visual Studio](../media/vs-2019/configure-new-project.png)

   Visual Studio vytvoří projekt. To je jednoduchá aplikace "Hello World", která volá <xref:System.Console.WriteLine?displayProperty=nameWithType> metodu pro zobrazení řetězcový literál "Hello World!" v okně konzoly (výstup programu).

   Po chvíli, by měl vypadat přibližně takto:

   ![Visual Studio – sada IDE](../media/vs-2019/overview-ide-console-app.png)

   Kód jazyka C# pro vaši aplikaci se zobrazí v okně editoru, což zabírá většinu prostoru. Všimněte si, že text je automaticky barevně zvýrazněné k označení různých částí kódu, jako jsou klíčová slova a typy. Kromě toho malé, svislé přerušované čáry v kódu označují, které složené závorky odpovídat mezi sebou a čísla řádků vám pomohou vyhledat kód později. Můžete také malé, zabalený mínus bloky kódu rozbalíte nebo sbalíte. Tento kód funkce osnovy vám umožňuje skrýt kód, který už nebudete potřebovat, a usnadnit tak minimalizovat zbytečné soubory na obrazovce. Soubory projektu jsou uvedeny na pravé straně v okně **Průzkumníka řešení**.

   ![Visual Studio integrované vývojové prostředí s červená pole](../media/vs-2019/overview-ide-console-app-red-boxes.png)

   K dispozici další nabídky a panely nástrojů, ale teď přejdeme teď.

1. Nyní spusťte aplikaci. To lze provést výběrem **spustit bez ladění** z **ladění** nabídky na řádku nabídek. Můžete také stisknout klávesu **Ctrl**+**F5**.

   ![Ladit > Spustit bez ladění nabídky](../media/overview-start-without-debugging.png)

   Visual Studio vytvoří aplikaci a otevře se okno konzoly se zprávou **Hello World!**. Nyní máte funkční aplikaci.

   ![Okno konzoly](../media/vs-2019/overview-console-window.png)

1. Zavřete okno konzoly stisknutím libovolné klávesy na klávesnici.

1. Přidejme do aplikace další kód. Přidejte následující kód jazyka C# před řádek, který říká `Console.WriteLine("Hello World!");`:

   ```csharp
   Console.WriteLine("\nWhat is your name?");
   var name = Console.ReadLine();
   ```

   Tento kód zobrazí **jak se jmenuješ?** v okně konzoly a potom počká, dokud uživatel zadá nějaký text, za nímž následuje **Enter** klíč.

1. Změňte řádek, který říká `Console.WriteLine("Hello World!");` v následujícím kódu:

   ```csharp
   Console.WriteLine($"\nHello {name}!");
   ```

1. Znovu spusťte aplikaci tak, že vyberete **ladění** > **spustit bez ladění** nebo stisknutím klávesy **Ctrl**+**F5**.

   Visual Studio znovu sestaví aplikaci a otevře se okno konzoly a vás vyzve k zadání název vaší.

1. Zadejte název v okně konzoly a stisknutím klávesy **Enter**.

   ![Okno konzoly](../media/vs-2019/overview-console-input.png)

1. Stisknutím jakékoli klávesy zavřete okno konzoly a zastavit spuštěný program.

::: moniker-end

## <a name="use-refactoring-and-intellisense"></a>Refaktoring a technologie IntelliSense

Podívejme se na několik způsobů, jak, který [refaktoring](../../ide/refactoring-in-visual-studio.md) a [IntelliSense](../../ide/using-intellisense.md) může pomoct kód efektivněji.

Nejprve přejmenujme `name` proměnné:

1. Dvakrát klikněte `name` proměnnou, která ho vyberte.

2. Zadejte nový název proměnné, **uživatelské jméno**.

   Všimněte si, že šedé pole se zobrazí kolem proměnnou a žárovky se zobrazí na okraji.

::: moniker range="vs-2017"

3. Vyberte ikonu žárovky k zobrazení dostupných [rychlé akce](../../ide/quick-actions.md). Vyberte **přejmenovat "název" na "username"**.

   ![Přejmenujte akci v sadě Visual Studio](../media/rename-quick-action.png)

   Proměnná je přejmenovat v projektu, který v našem případě je pouze dvě místa.

   ![Animovaný obrázek gif zobrazující refaktoring pro přejmenování v sadě Visual Studio](../media/rename-refactoring.gif)

::: moniker-end

::: moniker range=">=vs-2019"

3. Vyberte ikonu žárovky k zobrazení dostupných [rychlé akce](../../ide/quick-actions.md). Vyberte **přejmenovat "název" na "username"**.

   ![Přejmenujte akci v sadě Visual Studio](../media/vs-2019/rename-quick-action.png)

   Proměnná je přejmenovat v projektu, který v našem případě je pouze dvě místa.

::: moniker-end

4. Nyní Pojďme se podívat na IntelliSense. Pod řádek, který říká `Console.WriteLine($"\nHello {username}!");`, typ `DateTime now = DateTime.`.

   Pole zobrazuje jako objekty její členové <xref:System.DateTime> třídy. Popis aktuálně vybraného člena se navíc zobrazí v rámci samostatného pole.

   ![Seznam členů IntelliSense v sadě Visual Studio](../media/intellisense-list-members.png)

5. Vyberte člena s názvem **nyní**, což je vlastnost třídy, dvojitým kliknutím na ni nebo stisknutím klávesy **kartu**. Dokončení řádek kódu tak, že přidáte středníkem na konec.

6. Pod ním zadejte nebo vložte následující řádky kódu:

   ```csharp
   int dayOfYear = now.DayOfYear;

   Console.Write("Day of year: ");
   Console.WriteLine(dayOfYear);
   ```

   > [!TIP]
   > <xref:System.Console.Write%2A?displayProperty=nameWithType> se mírně liší na <xref:System.Console.WriteLine%2A?displayProperty=nameWithType> v tom, že po vytiskne nepřidá znakem ukončení řádku. To znamená, že další část textu, které je odesláno výstup vytiskne na stejném řádku. Myší nad každá z těchto metod v kódu zobrazíte jejich popis.

7. V dalším kroku použijeme refaktoring znovu provést trochu stručnější kód. Klikněte na proměnnou `now` v řádku `DateTime now = DateTime.Now;`.

   Všimněte si, že malou ikonu šroubovák se zobrazí na okraji na daném řádku.

8. Klikněte na ikonu šroubovák návrhy, které nabízí Visual Studio. V takovém případě se zobrazuje [dočasná proměnná na řádku](../../ide/reference/inline-temporary-variable.md) odebrat jediného řádku kódu beze změny celkové chování kódu refaktoringu kódu:

   ![Vložené dočasné proměnné refaktoring v sadě Visual Studio](../media/inline-temporary-variable-refactoring.png)

9. Klikněte na tlačítko **dočasná proměnná na řádku** Refaktorovat kód.

::: moniker range="vs-2017"

10. Spusťte program znovu stisknutím klávesy **Ctrl**+**F5**. Výstup bude vypadat přibližně takto:

    ![Okno konzoly s výstup programu](../media/overview-console-final.png)

::: moniker-end

::: moniker range=">=vs-2019"

10. Spusťte program znovu stisknutím klávesy **Ctrl**+**F5**. Výstup bude vypadat přibližně takto:

    ![Okno konzoly s výstup programu](../media/vs-2019/overview-console-final.png)

::: moniker-end

## <a name="debug-code"></a>Ladění kódu

Při psaní kódu, musíte ji spustit a otestovat pro chyby. Ladění systému Visual Studio vám umožní krokovat kód jeden příkaz najednou a kontrolovat proměnné, co využijete. Můžete nastavit *zarážky* , který svém vyvolání zastaví provádění kódu na konkrétní řádek. Můžete sledovat, jak hodnota proměnné změny jako kód spustí a další.

Pojďme nastavit zarážku pro její hodnota `username` proměnné při "v cestě" program.

1. Vyhledejte řádek kódu, který říká `Console.WriteLine($"\nHello {username}!");`. Nastavit zarážku na tomto řádku kódu, to znamená, aby program pozastaví provádění na tomto řádku, klikněte v levém okraji editoru. Můžete také kliknout na libovolné místo na řádek kódu a stiskněte klávesu **F9**.

   V levém okraji se zobrazí červený kruh a kód se zvýrazní červeně.

   ![Zarážku na řádek kódu v sadě Visual Studio](../media/breakpoint.png)

1. Spuštění ladění tak, že vyberete **ladění** > **spustit ladění** nebo stisknutím klávesy **F5**.

1. Když v okně konzoly se zobrazí a vyzve k zadání vaše jméno, zadejte jej a stiskněte klávesu **Enter**.

   Fokus vrátí do editoru kódu sady Visual Studio a na řádek kódu se zarážkou je zvýrazněn žlutě. To znamená, že se jedná o další řádek kódu, který se spustí program.

1. Najeďte myší `username` proměnnou můžete zobrazit její hodnotu. Alternativně je můžete kliknout pravým tlačítkem na `username` a vyberte **Přidat kukátko** chcete přidat proměnnou **Watch** okno, kde můžete také zobrazit její hodnotu.

   ![Hodnota proměnné během ladění v sadě Visual Studio](../media/debugging-variable-value.png)

1. Aby mohl program dokončen, stiskněte klávesu **F5** znovu.

Pokud chcete získat další informace o ladění v sadě Visual Studio, naleznete v tématu [prohlídka funkcí ladicího programu](../../debugger/debugger-feature-tour.md).

## <a name="customize-visual-studio"></a>Přizpůsobení sady Visual Studio

Uživatelské rozhraní sady Visual Studio, včetně změn si můžete přizpůsobit výchozí barevný motiv. Chcete-li změnit na **tmavě** motivu:

1. V panelu nabídky zvolte **nástroje** > **možnosti** otevřít **možnosti** dialogového okna.

::: moniker range="vs-2017"

2. Na **prostředí** > **Obecné** stránka Možnosti, změna **barevný motiv** výběru **tmavě**a klikněte na tlačítko **OK**.

   Barva motivu pro celý integrovaného vývojového prostředí se změní na **tmavě**.

   ![Visual Studio v tmavém motivu](../media/dark-theme.png)

::: moniker-end

::: moniker range=">=vs-2019"

2. Na **prostředí** > **Obecné** stránka Možnosti, změna **barevný motiv** výběru **tmavě**a klikněte na tlačítko **OK**.

   Barva motivu pro celý integrovaného vývojového prostředí se změní na **tmavě**.

   ![Visual Studio v tmavém motivu](../media/vs-2019/dark-theme.png)

::: moniker-end

Další informace o dalších způsobech mohli přizpůsobit integrovaného vývojového prostředí, najdete v článku [přizpůsobení sady Visual Studio](../../ide/personalizing-the-visual-studio-ide.md).