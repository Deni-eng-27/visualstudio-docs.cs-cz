---
title: "Visual Studio 2017 pro vývojáře .NET | Microsoft Docs"
description: "Přehled funkcí Visual Studio 2017 můžete napsat kód lepší .NET rychlejší."
author: kuhlenh
ms.author: kaseyu
manager: ghogen
ms.technology: vs-ide-general
ms.date: 11/08/2017
ms.topic: article
helpviewer_keywords: editor
ms.openlocfilehash: f8830b24aa763a1a59830d0dd15231673f1dfac3
ms.sourcegitcommit: fb751e41929f031d1a9247bc7c8727312539ad35
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/15/2017
---
# <a name="visual-studio-2017-for-net-developers"></a>Visual Studio 2017 pro vývojáře .NET

## <a name="smart-code-editor"></a>Editor inteligentní kódu
[Dokumentace: Pomocí IntelliSense](using-intellisense.md)  
[Dokumentace: Funkce Inteligentní editor](writing-code-in-the-code-and-text-editor.md)

Visual Studio obsahuje hluboké znalosti kódu prostřednictvím kompilátoru Roslyn poskytnout inteligentní úpravy funkcí, jako je zabarvení syntaxe, kód dokončení, kontrola pravopisu chybným proměnné, neimportovaných typu řešení, osnovy, struktura vizualizérech [Codelensu](find-code-changes-and-other-history-with-codelens.md), volání hierarchie, hover možnost rychlé informace, parametr nápovědy, jakož i nástroje pro refaktoring, použití rychlé akce a generování kódu.
 
![Visual Studio editor inteligentní kódu](../ide/media/VSIDE_Productivity_SmartCodeEditor.png "VSIDE_Productivity_SmartCodeEditor")  

## <a name="navigate-and-search-your-codebase"></a>Přejděte a hledání vaší základu kódu
[Dokumentace: Navigace v kódu](navigating-code.md)

Rychle přechod do souboru, typu, člen nebo symbol deklarace s přejít kódu .NET *přejděte na všechny* zástupce (**Ctrl + T**). Najít všechny odkazy literál nebo symbol v kódu, včetně odkazů mezi jazyky rozhraní .NET (**Shift + F12**). A pomocí našich cílové navigační příkazy můžete přejít přímo na symbol definice (**F12**) nebo implementace (**Ctrl + F12**).

![Přejděte na všechny a najít všechny odkazy](../ide/media/VSIDE_Productivity_Navigation.png "VSIDE_Productivity_Navigation")  

## <a name="live-code-analysis-for-code-quality"></a>Live analýzy kódu pro kvality kódu
[Dokumentaci: Refaktoring a rychlé akce](refactoring-code-generation-quick-actions.md)

Visual Studio má diagnostiky kódu za provozu můžete po zjištění chyby a potenciálně problematické kód zvýšení kvality vašeho kódu. Poskytujeme rychlé akce (**Ctrl +.**) k řešení problémů zjištěných napříč dokument, projekt nebo řešení. Povolit *analýzy úplné řešení* najít problémy v celé řešení i v případě, že nemáte ty soubory, otevřete v editoru. 

Kromě toho použít kód návrhy další osvědčených postupů, se zakázaným inzerováním nebo vygenerování kódu, refactor kódu a použít nové jazykové funkce s **Ctrl +.** Zástupce.

![Použít pro rychlé opravy a refaktoring pomocí žárovek nabídky](../ide/media/VSIDE_Productivity_CodeAnalysis.png "VSIDE_Productivity_CodeAnalysis")  

## <a name="unit-testing"></a>Testování částí
[Dokumentaci: Testování v sadě Visual Studio částí](../test/improve-code-quality.md)

Spuštění a ladění testů jednotek na základě Mstestu, NUnit nebo XUnit testování architektury pro každou aplikaci cílení na rozhraní .NET Framework, .NET Standard nebo .NET Core. Prozkoumat a zkontrolovat vaše testy *Průzkumníka testů* nebo okamžitě najdete na tom, jak změny kódu ovlivnit testů jednotek v editoru s *Live testování částí* (pouze verzi Enterprise). 

![Live testování v sadě Visual Studio částí](../ide/media/VSIDE_Productivity_LiveUnitTesting.png "VSIDE_Productivity_LiveUnitTesting")  

## <a name="code-consistency-and-style"></a>Kód konzistence a stylu
[Dokumentaci: Možnosti přenosné vlastního editoru](create-portable-custom-editor-options.md)  
[Dokumentace: EditorConfig kódu stylu nastavení pro rozhraní .NET](editorconfig-code-style-settings-reference.md)

Visual Studio umožňuje konvence kódování, zjistí kódování porušení stylu a poskytuje rychlé opravy Chcete-li opravit problémy styl s **Ctrl +.** Zástupce. Konfigurace a vynutit vašeho týmu, pojmenování, formátování a stylu pravidla vytváření kódu napříč úložiště – povolení potlačení hodnot na úrovni projektu a souborů – pomocí *EditorConfig*. 

![Konfigurace a vynutit konvence psaní kódu s EditorConfig](../ide/media/VSIDE_Productivity_CodeStyle.png "VSIDE_Productivity_CodeStyle")  

## <a name="debugging"></a>Ladění
[Dokumentace: Ladění v sadě Visual Studio](../debugger/index.md)

Visual Studio obsahuje Bezvadný ladicí program, který umožňuje ladit aplikace .NET cílení na rozhraní .NET Framework, .NET Standard a .NET Core. Přepněte a nastavte podmíněné zarážky (**F9**), krok do volání metod, vyhodnotit výrazy LINQ a lambda, nastavit proměnnou sleduje, připojte k procesy, prozkoumat vaše zásobník volání nebo dokonce vytvořit za provozu úpravy kódu při ladění pomocí  *Upravit a pokračovat*. 

Pokud vaše služba běží v Azure, použijte *snímku ladění* žádostí o vyřešení problémů v za provozu, nasazené cloudové aplikace ve Visual Studio 2017 Enterprise.

![Ladění v sadě Visual Studio](../ide/media/VSIDE_Productivity_Debugging.png "VSIDE_Productivity_Debugging")  

## <a name="version-control"></a>Správa verzí
[Dokumentace: Správa verzí v sadě Visual Studio](/vsts/index)

Použití git nebo TFVC k ukládání a aktualizujte kód v sadě Visual Studio. V editoru uspořádání místní změny s Team Explorer a sledovat čeká na potvrzení a změny pomocí stavového řádku. Nastavte průběžnou integraci a doručení v aplikaci Visual Studio s naše [průběžné doručování Tools pro Visual Studio](https://marketplace.visualstudio.com/items?itemName=VSIDEDevOpsMSFT.ContinuousDeliveryToolsforVisualStudio) rozšíření přijmout pracovní postup agile developer.

![Ovládací prvek v sadě Visual Studio zdroje](../ide/media/VSIDE_Productivity_SourceControl.png "VSIDE_Productivity_SourceControl")

## <a name="extensibility"></a>Rozšiřitelnost
[Dokumentace: Rozšíření sady Visual Studio](../extensibility/index.md)

Visual Studio obsahuje bohatý ekosystém rozšíření, které můžete nainstalovat nebo vytvořit, protože je budete potřebovat. Instalovat rozšíření z *Galerie rozšíření* nebo *Visual Studio Marketplace*, vytvoření vlastního editoru modulů plug-in s *VS SDK*, nebo vytvořit vlastní analyzátor kódu za provozu nebo refaktoring pomocí *SDK pro platformu .NET kompilátoru*. Stažením můžete najít další kód opravy a návrhy [analýza kódu Microsoft](https://marketplace.visualstudio.com/items?itemName=VisualStudioPlatformTeam.MicrosoftCodeAnalysis2017) rozšíření. 

![Galerie rozšíření sady Visual Studio](../ide/media/VSIDE_Productivity_Extensibility.png "VSIDE_Productivity_Extensibility")  

## <a name="popular-extensions--shortcuts"></a>Oblíbená rozšíření & zástupců
Pokud jsou pocházejících z jiného IDE nebo kódování prostředí, může se stát, některou z následujících přípon užitečné instalaci:
- [EMACS emulace](https://marketplace.visualstudio.com/items?itemName=VisualStudioProductTeam.Emacsemulation)
- [Klávesové zkratky pro Visual Studio (ReSharper/IntelliJ)](https://marketplace.visualstudio.com/items?itemName=JustinClareburtMSFT.HotKeys2017-KeyboardShortcuts)
- [VSVim](https://marketplace.visualstudio.com/items?itemName=JaredParMSFT.VsVim)

| Zástupce (všechny profily) | Příkaz | Popis |
|-|-|-| 
| **CTRL + T** | Přejděte na všechny | Přejděte na všechny deklarace souboru nebo typ/člen nebo symbol |
| **F12** (také **Ctrl + kliknutí**) | Přechod na definici | Přejděte do kterých byla definována symbol |
| **CTRL + F12** | Přejít na implementaci | Přejděte do jeho různé implementace ze základní typ nebo člen |
| **SHIFT + F12** | Najít všechny odkazy | Zobrazit všechny symbol nebo literálu odkazy |
| **CTRL +.** (také **Alt + zadejte** v profilu C#) | Rychlé akce a refaktoringy | Zobrazit, jaké kód opravy, akce generování kódu, refaktoring nebo jiných rychlé akce jsou k dispozici na výběr kurzoru pozici nebo kód |
| **Kombinace kláves CTRL + Q** | Snadné spuštění | Hledání všechna nastavení sady Visual Studio |
| **F5** | Spuštění ladění | Spuštění ladění aplikace |
| **CTRL + F5** | Spustit bez ladění | Místní spuštění aplikace bez ladění |
| **CTRL + K, D** (výchozí profil) nebo **Ctrl + E, D** (C# profil) | Formátovat dokument | Vyčistí formátování porušení v souboru na základě vašeho znaky, mezery a nastavení odsazení |
| **CTRL +\,E** (výchozí profil) nebo **Ctrl + W, E** (C# profil) | Seznam chyb zobrazit | Zobrazit všechny chyby v dokument, projekt nebo řešení |


