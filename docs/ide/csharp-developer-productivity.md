---
title: Zvýšení produktivity pro vývoj pro .NET
description: Přehled navigace, analýza kódu, testování částí a další funkce, které vám pomůžou psát lepší kód .NET rychleji.
author: kuhlenh
ms.author: jillfra
manager: jillfra
ms.date: 04/25/2019
ms.topic: conceptual
helpviewer_keywords:
- editor
ms.workload:
- dotnet
ms.openlocfilehash: 69dd92c2dae1a042e37601917bcdef628400d8bf
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/19/2019
ms.locfileid: "72652580"
---
# <a name="visual-studio-productivity-guide-for-c-developers"></a>Průvodce produktivitou sady Visual C# Studio pro vývojáře

Přečtěte si, jak Visual Studio umožňuje vývojářům zvýšit produktivitu než kdy dřív. Využijte naše vylepšení výkonu a produktivity, jako je navigace do dekompilovaných sestavení, návrhy názvů proměnných při psaní, zobrazení hierarchie v **Průzkumníku testů**, přejděte na vše (**CTRL** +**t**) a přejděte na soubor/ deklarace typu/člen/symbol, inteligentní **pomocná výjimka**, konfigurace a vynucování stylu kódu a mnoho refaktoringů a oprav kódu.

## <a name="im-used-to-keyboard-shortcuts-from-a-different-editor"></a>Používám klávesové zkratky z jiného editoru

::: moniker range="vs-2017"

**Novinka ve Visual Studiu 2017 verze 15,8**

::: moniker-end

Pokud přecházíte z jiného rozhraní IDE nebo prostředí kódování, můžete změnit schéma klávesnice na *Visual Studio Code* nebo *reostřejšíer (Visual Studio)* :

![Schémata klávesnice v aplikaci Visual Studio](../ide/media/VS2017Guide-Keyboard.png)

Některá rozšíření také nabízejí schémata klávesnice:

- [Klávesové zkratky pro Visual Studio (ReSharper/IntelliJ)](https://marketplace.visualstudio.com/items?itemName=JustinClareburtMSFT.HotKeys)
- [Emulace (Emacs)](https://marketplace.visualstudio.com/items?itemName=JustinClareburtMSFT.EmacsEmulation)
- [VSVim](https://marketplace.visualstudio.com/items?itemName=JaredParMSFT.VsVim)

Níže jsou uvedené oblíbené zkratky pro Visual Studio:

| Zástupce (všechny profily) | Příkaz | Popis |
|-|-|-|
| **Ctrl**+**t** | Přejít na vše | Přejít k libovolnému souboru, typu, členu nebo deklaraci symbolu |
| **F12** (také **CTRL** +**kliknutí**) | Přejít k definici | Přejít na místo, kde je symbol definovaný |
| **Ctrl** +**F12** | Přejít k implementaci | Přechod ze základního typu nebo členu na jeho různé implementace |
| **Shift** +**F12** | Najít všechny odkazy | Zobrazit všechny odkazy na symboly nebo literály |
| **Ctrl** + **.** (také **Alt** +**zadat** v C# profilu) | Rychlé akce a refaktoringy | Podívejte se, jaké opravy kódu, akce generování kódu, refaktoringy nebo jiné rychlé akce jsou k dispozici na pozici kurzoru nebo výběru kódu. |
| **Ctrl** +**D** | Duplicitní řádek | Duplikuje řádek kódu, ve kterém je kurzor (k dispozici v **aplikaci Visual Studio 2017 verze 15,6** a novější) |
| **Shift** +**Alt** + **+** / **-** | Výběr rozšíření/smlouvy | Rozšíří nebo vybírá aktuální výběr v editoru (k dispozici v **aplikaci Visual Studio 2017 verze 15,5** a novější). |
| **Shift**  + **ALT**  +  **.** | Vložit další vyhovující blikající kurzor | Přidá výběr a blikající kurzor na další místo, které odpovídá aktuálnímu výběru (k dispozici v **aplikaci Visual Studio 2017 verze 15,8** a novější). |
| **Ctrl** +**Q** | Hledat | Vyhledat všechna nastavení sady Visual Studio |
| **Stisknutím** | Spustit ladění | Spuštění ladění aplikace |
| **Ctrl** +**F5** | Spustit bez ladění | Místní spuštění aplikace bez ladění |
| **CTRL** +**K**,**D** (výchozí profil) nebo **CTRL** +**E**,**D** (C# profil) | Formátovat dokument | Vyčistí porušení formátování v souboru na základě nastavení nového řádku, mezer a odsazení. |
| **CTRL** + **\\** ,**CTRL** +**E** (výchozí profil) nebo **CTRL** +**W**,**E** (C# Profile) | Zobrazit Seznam chyb | Zobrazit všechny chyby v dokumentu, projektu nebo řešení |
| **Alt**  + **Page Up/Page Down** | Přejít na další/předchozí problém | Přejít na předchozí/další chybu, upozornění, návrh v dokumentu (k dispozici v **aplikaci Visual Studio 2017 verze 15,8** a novější) |
| **Ctrl** +**K**, **/** | Přepnout komentář na jeden řádek/zrušit komentář | Tento příkaz přidá nebo odebere Jednořádkový komentář v závislosti na tom, jestli je váš výběr už připsaný do komentáře. |
| **Ctrl** +**SHIFT** + **/** | Přepnout komentář k bloku/zrušit komentář | Tento příkaz přidá nebo odebere komentáře blokování v závislosti na tom, co jste vybrali. |

> [!NOTE]
> Některá rozšíření odváže výchozí klávesové zkratky sady Visual Studio. Pokud chcete použít výše uvedené příkazy, obnovte vazby klíčů na výchozí hodnoty sady Visual Studio, a to tak, že na panelu **nástroje**  > ete**Nastavení importu a exportu**  > **resetování všech nastavení** nebo **nástrojů**  > **Možnosti**  > **klávesnice.** 0**resetovat**.

Další informace o klávesových zkratkách a příkazech najdete v tématech [zástupci produktivity](../ide/productivity-shortcuts.md) a [Oblíbené klávesové zkratky](default-keyboard-shortcuts-for-frequently-used-commands-in-visual-studio.md).

## <a name="navigate-quickly-to-files-or-types"></a>Rychlé procházení souborů nebo typů

Visual Studio obsahuje funkci s názvem **Přejít na vše** (**CTRL** +**t**). Možnost **Přejít na vše** vám umožní rychle přejít na libovolný soubor, typ, člen nebo deklaraci symbolu.

- Změňte umístění tohoto panelu hledání nebo vypněte živý náhled navigace pomocí ikony **ozubeného kolečka** .
- Filtrovat výsledky pomocí syntaxe, jako je například `t mytype`.
- Umožňuje určit rozsah hledání pouze na aktuální dokument.
- Ve stylu CamelCase se shoduje s případem, který je podporován.

![Přejít na vše v aplikaci Visual Studio](../ide/media/VS2017Guide-go-to-all.png)

## <a name="enforce-code-style-rules"></a>Vynutilit pravidla stylu kódu

Soubor EditorConfig můžete použít k codifyí konvence kódování a jejich cestování se zdrojem.

![Vynucení stylu kódu v aplikaci Visual Studio](../ide/media/VSGuide_CodeStyle.png)

- Přidejte výchozí nebo. EditorConfig soubor s ČISTÝM stylem do projektu výběrem možnosti **přidat**  > **novou položku**. V dialogovém okně **Přidat novou položku** vyhledejte "editorconfig". Vyberte jednu z šablon položek **souboru editorconfig** a pak zvolte **Přidat**.

   ![Šablony položek EditorConfig v aplikaci Visual Studio](media/editorconfig-item-templates.png)

::: moniker range=">=vs-2019"

- Automaticky vytvořte soubor *. editorconfig* na základě nastavení stylu kódu v **nabídce nástroje** > **možnosti** > **textový editor** > **C#** > **stylu kódu**.

   ![Generovat soubor. editorconfig z nastavení ve VS 2019](media/vs-2019/generate-editorconfig-file.png)

::: moniker-end

- [Funkce odvození kódu](/visualstudio/intellicode/code-style-inference) IntelliCode pro Visual Studio odvodí vaše styly kódu z existujícího kódu. Pak vytvoří neprázdný soubor EditorConfig s předem definovanými preferencemi stylu kódu.

Podívejte se na dokumentaci [Možnosti konvence kódování .NET](editorconfig-code-style-settings-reference.md) , která obsahuje také příklad kompletního souboru EditorConfig.

::: moniker range=">=vs-2019"

## <a name="code-cleanup"></a>Vyčištění kódu

Visual Studio poskytuje formátování souboru kódu, včetně předvoleb stylu kódu, prostřednictvím funkce **Vyčištění kódu** na vyžádání. Chcete-li spustit nástroj Vyčištění kódu, klikněte na ikonu Broom ve spodní části editoru nebo stiskněte klávesovou **zkratku ctrl** +**K**, **CTRL** +**E**.

![Tlačítko pro vyčištění kódu v aplikaci Visual Studio 2019](media/execute-code-cleanup.png)

Můžete také spustit vyčištění kódu v celém projektu nebo řešení. Klikněte pravým tlačítkem myši na název projektu nebo řešení v **Průzkumník řešení**, vyberte **Analýza a vyčištění kódu**a pak vyberte **Spustit vyčištění kódu**.

![Spustit čištění kódu v celém projektu nebo řešení](media/run-code-cleanup-project-solution.png)

Kromě formátování souboru pro mezery, odsazení, et zajistila, **Nástroj pro vyčištění kódu** používá také vybrané styly kódu. Vaše předvolby pro jednotlivé styly kódu jsou čteny ze [souboru EditorConfig](code-styles-and-code-cleanup.md#code-styles-in-editorconfig-files), pokud máte jeden pro projekt, nebo z [Nastavení stylu kódu](code-styles-and-code-cleanup.md#code-styles-in-the-options-dialog-box) v dialogovém okně **Možnosti** .

::: moniker-end

## <a name="refactorings-and-code-fixes"></a>Refaktoring a opravy kódu

Visual Studio obsahuje mnoho refaktoringů, akcí generování kódu a oprav kódu. Červené vlnovky reprezentují chyby, zelené vlnovky reprezentují upozornění a tři šedé tečky reprezentují návrhy kódu. K opravám kódu můžete získat přístup kliknutím na žárovku nebo na ikonu Screwdriver nebo stisknutím **kombinace kláves Ctrl** + **.** nebo **Alt** +**ENTER**. Každá oprava je dodávána s oknem náhledu, které zobrazuje informace o živém kódu, jak oprava funguje.

Mezi oblíbené rychlé opravy a refaktoringy patří:

- přejmenování
- extrahování metody
- Změnit podpis metody
- Generovat konstruktor
- Generate – metoda
- Přesunout typ do souboru
- Přidat kontrolu null
- Přidat parametr
- Odebrat nepotřebné direktivy using
- Smyčka foreach do dotazu LINQ nebo na metodu LINQ
- Vyžádané členy nahoru

Další informace najdete v tématu [funkce pro generování kódu](code-generation-in-visual-studio.md).

Můžete [nainstalovat analyzátory FxCop](../code-quality/install-fxcop-analyzers.md) pro označení problémů s kódem. Nebo zapište vlastní refaktoring nebo opravu kódu pomocí [analyzátorů Roslyn](https://github.com/dotnet/roslyn/wiki/Getting-Started-Writing-a-Custom-Analyzer-&-Code-Fix).

Několik členů komunity má napsaná bezplatná rozšíření, která přidávají další kontroly kódu:

- [Roslynator](https://marketplace.visualstudio.com/items?itemName=josefpihrt.Roslynator2017)
- [SonarLint pro Visual Studio](https://marketplace.visualstudio.com/items?itemName=SonarSource.SonarLintforVisualStudio2017)
- [StyleCopAnalyzers](https://www.nuget.org/packages/stylecop.analyzers/)
- [CodeCracker](https://www.nuget.org/packages/codecracker.CSharp/)

![Refaktoring v aplikaci Visual Studio](../ide/media/VSGuide_CodeAnalysis.png)

## <a name="find-usages-go-to-implementation-and-navigate-to-decompiled-assemblies"></a>Najít použití, přejít k implementaci a přejít na dekompilovaná sestavení

Visual Studio obsahuje mnoho funkcí, které vám pomůžou vyhledávat a [Procházet váš kód](../ide/navigating-code.md).

| Funkce | Zástupce | Podrobnosti a vylepšení |
|- | - | -|
| Najít všechny odkazy | **Shift** +**F12**| Výsledky jsou barevné a lze je seskupit podle typu projektu, definice a odkazu, jako je například čtení nebo zápis. Můžete také zamknout výsledky. |
| Přejít k implementaci | **Ctrl** +**F12** | Pomocí možnosti přejít k definici na klíčovém slově `override` můžete přejít k přepsanému členu. |
| Přejít k definici | **F12** nebo **CTRL** +**klikněte na**| Když kliknete na tlačítko Přejít na definici, stiskněte klávesu **CTRL** |
| Náhled definice | **Alt** +**F12** | Vložené zobrazení definice |
| Vizualizér struktury | Šedá, tečkované – čáry mezi závorkami | Zobrazení struktury kódu najeďte myší |
| Navigace do dekompilovaných sestavení | **F12** nebo **CTRL** +**klikněte na** | Povolením funkce přejděte na externí zdroj (dekompilováno s ILSpy): **nástroje**  > **Možnosti**  > **textový Editor**  > **C#**  > **pokročilý** 0**Povolit navigaci na dekompilované zdroje.** . |

![Přejít na vše a najít všechny odkazy](../ide/media/VSIDE_Productivity_Navigation.png)

## <a name="improved-intellisense"></a>Vylepšená technologie IntelliSense

Použijte IntelliCode pro Visual Studio k získání [kontextového dokončování kódu](/visualstudio/intellicode/intellicode-visual-studio) namísto pouze abecedního seznamu. Můžete také vytvořit [vlastní model IntelliSense](/visualstudio/intellicode/custom-model-faq) na základě vlastních knihoven specifických pro doménu.

## <a name="unit-testing"></a>Testování jednotek

Od sady Visual Studio 2017 existuje mnoho vylepšení prostředí testování. Můžete testovat pomocí testovacích rozhraní MSTest V1, MSTest v2, NUnit nebo XUnit.

- Zjišťování testů **Průzkumníka testů** je rychlé.

- Uspořádejte své testy v **Průzkumníku testů** pomocí *hierarchického řazení*.

   ![Zobrazení hierarchie pro text Explorer v aplikaci Visual Studio](../ide/media/VSGuide_Testing.png)

- [Live Unit Testing](../test/live-unit-testing.md) průběžně spouští testy ovlivněné změnami kódu a aktualizuje ikony vloženého editoru, které vám umožní znát stav testů. Zahrnutí nebo vyloučení konkrétních testů nebo testovacích projektů ze sady Live test. (Pouze edice Visual Studio Enterprise.)

## <a name="debugging"></a>Ladění

Mezi možnosti ladění v aplikaci Visual Studio patří:

::: moniker range=">=vs-2019"

- Možnost Hledat řetězec v oknech **kukátka**, **Automatické**hodnoty a **místní** hodnoty.
- *Klikněte na tlačítko*, které vám umožní umístit ukazatel myši na řádek kódu, zobrazit zelenou ikonu přehrávání a spustit program, dokud nedosáhne tohoto řádku.
- **Pomocný Pomocník pro výjimky**, který do nejvyšší úrovně v dialogovém okně umístí nejdůležitější informace, například o tom, která proměnná je `null` v `NullReferenceException`.
- [Krok zpět ladění](../debugger/view-historical-application-state.md)vám umožní přejít zpět na předchozí zarážky nebo kroky a zobrazit stav aplikace, stejně jako v minulosti.
- [Ladění snímků](/azure/application-insights/app-insights-snapshot-debugger), které umožňuje prozkoumat stav živé webové aplikace v okamžiku, kdy byla vyvolána výjimka (musí být v Azure).

::: moniker-end

::: moniker range="vs-2017"

- *Klikněte na tlačítko*, které vám umožní umístit ukazatel myši na řádek kódu, zobrazit zelenou ikonu přehrávání a spustit program, dokud nedosáhne tohoto řádku.
- **Pomocný Pomocník pro výjimky**, který do nejvyšší úrovně v dialogovém okně umístí nejdůležitější informace, například o tom, která proměnná je `null` v `NullReferenceException`.
- [Krok zpět ladění](../debugger/view-historical-application-state.md)vám umožní přejít zpět na předchozí zarážky nebo kroky a zobrazit stav aplikace, stejně jako v minulosti.
- [Ladění snímků](/azure/application-insights/app-insights-snapshot-debugger), které umožňuje prozkoumat stav živé webové aplikace v okamžiku, kdy byla vyvolána výjimka (musí být v Azure).

::: moniker-end

![Pomocník pro výjimky v aplikaci Visual Studio](../ide/media/VSGuide_Debugging.png)

## <a name="version-control"></a>Správa verzí

Můžete použít Git nebo TFVC k uložení a aktualizaci kódu v aplikaci Visual Studio.

::: moniker range=">=vs-2019"

- Nainstalujte žádosti o přijetí změn [pro Visual Studio](https://marketplace.visualstudio.com/items?itemName=vsideversioncontrolmsft.pr4vs) , které vám umožní vytvořit, zkontrolovat, rezervovat a spustit žádosti o přijetí změn bez nutnosti opustit aplikaci Visual Studio.

::: moniker-end

- Uspořádejte místní změny v [Team Explorer](reference/team-explorer-reference.md) a pomocí stavového řádku Sledujte nevyřízená potvrzení a změny.

- Pomocí [nástrojů pro průběžné doručování pro rozšíření sady Visual Studio](https://marketplace.visualstudio.com/items?itemName=VSIDEDevOpsMSFT.ContinuousDeliveryToolsforVisualStudio) nastavte průběžnou integraci a doručování pro projekty ASP.NET uvnitř sady Visual Studio.

![Správa zdrojového kódu v aplikaci Visual Studio](../ide/media/VSIDE_Productivity_SourceControl.png)

## <a name="what-other-features-should-i-know-about"></a>O kterých dalších funkcích mám vědět?

Tady je seznam funkcí editoru a produktivity, které umožňují efektivnější psaní kódu. Je možné, že některé funkce budou potřeba povolit, protože jsou ve výchozím nastavení vypnuté (můžou na vašem počítači indexovat objekty, jsou kontroverzním nebo jsou aktuálně experimentální).

| Funkce | Podrobnosti | Jak povolit |
|-|-|-|
| Najít soubor v Průzkumník řešení | Zvýrazní aktivní soubor v **Průzkumník řešení** | **Nástroje**  > **Možnosti**  > **projekty a řešení**  > **sledovat aktivní položku v Průzkumník řešení** |
| Přidat použití pro typy v referenčních sestaveních a balíčcích NuGet | Zobrazuje žárovku chyby s opravou kódu pro instalaci balíčku NuGet pro neodkazový typ. | **Nástroje**  > **Možnosti**  > **textový editor**  > **C#**  > **Pokročilé** 0**navrhnout použití typů v referenčních sestaveních** a **navrhnout použití typů v balíčcích NuGet** |
| Povolení úplné analýzy řešení | Zobrazit všechny chyby ve vašem řešení v **Seznam chyb** | **Nástroje**  > **Možnosti**  > **textový Editor**  > **C#**  > **pokročilý** 0**Povolit úplnou analýzu řešení** |
| Povolit navigaci na dekompilované zdroje | Umožňuje přejít na definici typů/členů z externích zdrojů a použít Decompiler ILSpy k zobrazení těla metody. | **Nástroje**  > **Možnosti**  > **textový Editor**  > **C#**  > **pokročilý** 0**Povolit navigaci na dekompilované zdroje** |
| Režim dokončení/návrhu | Změní chování při dokončování v IntelliSense. Vývojáři, kteří IntelliJ pozadí, obvykle používají jiné než výchozí nastavení. | **Nabídka**  > **upravit**  > **IntelliSense**  > **Přepnout režim dokončení** |
| [CodeLens](../ide/find-code-changes-and-other-history-with-codelens.md) | Zobrazí referenční informace o kódu a historii změn v editoru. (Indikátory CodeLens správy zdrojového kódu nejsou k dispozici v edici Visual Studio Community Edition.) | **Nástroje**  > **Možnosti**  > **textový editor**  > **všechny jazyky**  > **CodeLens** |
| [Fragmenty kódu](../ide/visual-csharp-code-snippets.md) | Běžný často používaný kód s kódem Help unstub | Zadejte název fragmentu a dvakrát stiskněte klávesu **TAB** . |
