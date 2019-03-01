---
title: Novinky v sadě Visual Studio 2019
titleSuffix: ''
description: Další informace o nových funkcích sady Visual Studio 2019.
ms.date: 02/27/2019
helpviewer_keywords:
- Visual Studio, what's new
- what's new [Visual Studio]
ms.assetid: 00bec66b-bcee-46f5-91d9-f73a2b469744
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.prod: visual-studio-dev16
ms.topic: conceptual
ms.workload:
- multiple
ms.openlocfilehash: c4475836a9d4cdd394bff78280c5c075dd960e1d
ms.sourcegitcommit: 87d7123c09812534b7b08743de4d11d6433eaa13
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/01/2019
ms.locfileid: "57223543"
---
# <a name="whats-new-in-visual-studio-2019"></a>Novinky v sadě Visual Studio 2019

**Aktualizováno pro [Release Candidate (RC)](/visualstudio/releases/2019/release-notes/)**

>[!div class="button"]
>[Stáhněte si verzi RC:](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019+rc)

Visual Studio 2019 zahrnuje mnoho Obecná vylepšení spolu s novými funkcemi, které optimalizovat produktivitu a spolupráci mezi týmy. Ať už používáte Visual Studio poprvé nebo jste dosud používali ho let, budete moct využívat jeho funkce pro všechny aspekty životního cyklu vývoje&mdash;z zjednodušené vytváření a kód stavu řízení projektů, tým – a spolupráci pracovní postupy open source.<br/><br/>

>[!VIDEO https://channel9.msdn.com/Events/Connect/Microsoft-Connect--2018/D190/player]

Tady je podrobný rekapitulace toho, co má Visual Studio nabízí:

* **[Osobní a zvýšení produktivity týmu](#personal-and-team-productivity)**. Produktivita pro všechny uživatele, kde jsou nejvíc.
* **[Podpora moderního vývoje](#modern-development-support)**. Podpora pro projekty aktuální a budoucí řešení.
* **[Průběžné inovace](#continuous-innovation)**. Kód inteligentní s podporou inteligentní, s využitím cloudu.

> [!NOTE]
> Úplný seznam nových funkcí a funkce v aplikaci Visual Studio 2019, najdete v článku [poznámky k verzi RC](/visualstudio/releases/2019/release-notes/) a [poznámky k verzi Preview 4](/visualstudio/releases/2019/release-notes-preview/). Další informace o obou těchto nedávno vydané aktualizace, najdete v článku [Visual Studio. 2019 Release Candidate nyní k dispozici](https://devblogs.microsoft.com/visualstudio/visual-studio-2019-release-candidate-rc-now-available/) blogový příspěvek.

## <a name="personal-and-team-productivity"></a>Osobní a produktivitu týmu

Je že jsou vylepšení výkonu nejvyšší prioritu v každé verzi sady Visual Studio, ale vpravo se tam s ní se zvyšuje vaši produktivitu. Zde je, jak můžeme pomoct s ním.

### <a name="new-start-window"></a>Nový časový interval pro spuštění

První věc, kterou zjistíte, když spustíte Visual Studio 2019 je její nové okno start.

   ![Nové okno start v aplikaci Visual Studio 2019](media/start-window.png)

Toto nové okno start vám nabídne možnosti, jak klonovat nebo podívejte se na kód, otevřete projekt nebo řešení, otevřít místní složku nebo vytvořte nový projekt. Tyto možnosti se zobrazí v dialogovém okně jednoduché pomůže obou začátečníky a získat kód rychle Pokročilí uživatelé sady Visual Studio.

Další informace najdete v tématu [získat kód: Jak jsme navrhli nové okno Visual Studio start](https://devblogs.microsoft.com/visualstudio/get-to-code-how-we-designed-the-new-visual-studio-start-window/) blogový příspěvek.

### <a name="better-search"></a>Lepší vyhledávání

Dříve označované jako Snadné spuštění, naše nové rozhraní pro hledání je rychlejší a efektivnější. Nyní výsledky hledání zobrazeny dynamicky během psaní. A výsledky hledání obsahují klávesové zkratky pro příkazy, takže můžete snadno pamatovat pro budoucí použití.

   ![Nové funkce hledání v aplikaci Visual Studio 2019](media/search-feature.png)

Jestli chcete pro příkazy a nastavení nebo další užitečné věci, nová funkce vyhledávání je snazší najít, co hledáte.

### <a name="one-click-code-cleanup"></a>Vyčištění kódu jedním kliknutím

Spárovat s nový indikátor stavu dokumentu je nový příkaz vyčištění kódu. Tento nový příkaz slouží k identifikaci a potom opravit upozornění a návrhy kliknutím na tlačítko.

   ![Nové funkce vyčištění kódu v aplikaci Visual Studio 2019](media/code-cleanup.png)

Čištění formátovat kód, který se použije všechny opravy kódu jak navrhovaly [aktuální nastavení](code-styles-and-quick-actions.md), [soubory .editorconfig](create-portable-custom-editor-options.md), nebo [analyzátory Roslyn](../code-quality/roslyn-analyzers-overview.md).

### <a name="debugger-improvements"></a>Vylepšení ladicího programu

#### <a name="search-within-a-watch-window-and-format-watch-values"></a>Vyhledávání v rámci okna kukátka a formátování hodnot sledování

Pravděpodobně jste došlo před, hledání v okně kukátko pro řetězec ze sady hodnot. V aplikaci Visual Studio 2019 jsme přidali vyhledávání v oknech sledovat, místní hodnoty a automatické hodnoty a umožňují najít objekty a hodnoty, které hledáte.

Můžete také formátovat, jak se zobrazí hodnota v oknech sledovat, místní hodnoty a automatické hodnoty.  Dvakrát klikněte na jednu z položek v některém z windows a přidejte čárku (",") pro přístup k seznamu rozevírací seznam specifikátorů formátu je to možné, z nichž každý obsahuje popis jeho zamýšlený efekt.

   ![Nové kukátko okno Formát hodnoty funkci a ve Visual Studio 2019](media/search-watch-window.png)

Další informace najdete v tématu [zdokonaleno ve Visual Studio 2019: Hledání objektů a vlastností v okně kukátka, automatické hodnoty a místní hodnoty Windows](https://devblogs.microsoft.com/visualstudio/enhanced-in-visual-studio-2019-search-for-objects-and-properties-in-the-watch-autos-and-locals-windows/) blogový příspěvek.

### <a name="visual-studio-live-share"></a>Visual Studio za sdílené složky

[Visual Studio Live Share](https://visualstudio.microsoft.com/services/live-share/) je služba pro vývojáře, která umožňuje sdílet základ kódu a jeho kontextu s programujete a získat rychlé obousměrné spolupráci přímo z Visual Studia. S Live Share programujete můžete přečíst, přejděte, upravit a ladit projekt, který jste sdíleli s nimi a učinit snadno a bezpečně.

A s Visual Studio 2019, tato služba nainstaluje ve výchozím nastavení.

![Animovaný GIF, který zobrazuje spolupráci funkce Live Share v aplikaci Visual Studio 2019](media/live-share-collaboration.gif)

Další informace najdete v tématu [Visual Studio Live Share pro revize kódu v reálném čase a interaktivní vzdělávání](https://devblogs.microsoft.com/visualstudio/visual-studio-live-share-for-real-time-code-reviews-and-interactive-education/) blogový příspěvek.

## <a name="modern-development-support"></a>Podpora moderního vývoje

### <a name="manage-pull-requests-prs-from-the-ide"></a>Správa žádostí o přijetí změn (žádosti o přijetí změn) v prostředí IDE

Zavádíme nové rozšíření, které si můžete stáhnout pomocí Visual Studio 2019. Pomocí této nové rozšíření, můžete zkontrolovat, spustit a dokonce i ladění žádosti o přijetí změn od týmu, aniž byste museli opustit integrované vývojové prostředí sady Visual Studio [(integrované vývojové prostředí)](../get-started/visual-studio-ide.md). Jsme podporu kódu v úložišti Azure ještě dnes, ale rozšiřují podporu Githubu a zdokonalovat celkové prostředí.

Abyste mohli hned začít, stáhněte si [žádosti o přijetí změn pro sadu Visual Studio](https://aka.ms/pr4vs) rozšíření z Visual Studio Marketplace.

### <a name="develop-with-net-core-3-preview"></a>Vývoj s využitím .NET Core 3 ve verzi Preview

Ve verzi preview verze sady Visual Studio 2019 podporuje vytváření [.NET Core 3](https://dotnet.microsoft.com/download/dotnet-core/3.0) aplikací pro libovolnou platformu. Budeme nadále podporovat a zlepšit multiplatformní vývoj v jazyce C++ a .NET vývoj mobilních aplikací pro iOS a Android pomocí Xamarinu.

   ![Vývoj aplikací pomocí .NET Core 3 ve verzi Preview v aplikaci Visual Studio 2019](media/dot-net-core-three-dev.png)

Další informace naleznete na následujících stránkách:

* [.NET core 3 Preview 1](https://github.com/dotnet/core/blob/master/release-notes/3.0/preview/3.0.0-preview1.md) a [.NET Core 3 ve verzi Preview 2](https://github.com/dotnet/core/blob/master/release-notes/3.0/preview/3.0.0-preview2.md) zpráva k vydání verze
* [Ohlašujeme .NET Core 3 Preview 1](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-preview-1-and-open-sourcing-windows-desktop-frameworks/) a [Ohlašujeme .NET Core 3 ve verzi Preview 2](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-preview-2/) blogové příspěvky

## <a name="continuous-innovation"></a>Průběžné inovace

### <a name="per-monitor-aware-pma-rendering"></a>Clustery vykreslování (PMA) na monitorování

Pokud používáte monitorování, které jsou nakonfigurovány s jiným zobrazením měřítko nebo vzdáleně připojit k počítači s použitím zobrazení škálování faktorů, které se liší od hlavní zařízení, můžete všimnout, že Visual Studio rozmazaný nebo vykreslí nesprávné měřítko.

Ve verzi Visual Studio 2019 jsme se rozhodli první kroky k zabezpečení aplikace Visual Studio (PMA) aplikace pracující s za monitorování. Pokládáme základní práce, které vám umožní sadě Visual Studio správně vykreslit, bez ohledu na to, co zobrazí měřítko, které používáte.

   ![Clustery vykreslování (PMA) v aplikaci Visual Studio 2019 za monitorování](media/per-monitor-aware-dpi-scaling.png)

Další informace najdete v tématu [lepší prostředí pro více monitorů s Visual Studio 2019](https://devblogs.microsoft.com/visualstudio/a-better-multi-monitor-experience-with-visual-studio-2019/) blogový příspěvek.

### <a name="visual-studio-intellicode"></a>Visual Studio IntelliCode

[Visual Studio IntelliCode](/visualstudio/intellicode/) je rozšíření, která vylepšuje své úsilí vývoje softwaru pomocí umělé inteligence (AI). IntelliCode železniční napříč 2 000 open-source projektů na Githubu&mdash;každý s více než 100 hvězdiček&mdash;ke generování doporučení.

Tady je několik způsobů, jak Visual Studio IntelliCode může pomoct zvýšit produktivitu práce:

* Doručování dokončování s ohledem na kontext kódu
* Příručka pro vývojáře dodržovat vzory a styly jejich tým
* Najít problémy s kódu obtížné catch
* Revize kódu fokus kreslením upozornit na oblasti, které jsou opravdu důležité.

 ![Příklad návrhem technologie IntelliSense](media/intellicode-intellisense-suggestion.png)

Zpočátku podporujeme pouze C# když jsme první předběžně IntelliCode rozšíření pro Visual Studio. Nyní přidali jsme podporu pro C++ a XAML v sadě Visual Studio, příliš.

A pokud používáte C#, přidali jsme také možnost pro trénování modelu vlastní na váš vlastní kód.

Další informace o nedávných aktualizacích najdete v tématu [Visual Studio IntelliCode podporuje více jazyků a učí z vašeho kódu](https://devblogs.microsoft.com/visualstudio/visual-studio-intellicode-supports-more-languages-and-learns-from-your-code/) blogový příspěvek. A další informace o rozšíření a jak ho můžete stáhnout, najdete v článku [Visual Studio IntelliCode - Preview](https://go.microsoft.com/fwlink/?linkid=872707) stránce Microsoft DevLabs.

## <a name="give-us-feedback"></a>Sdělte nám svůj názor

Proč odeslat zpětnou vazbu týmu sady Visual Studio? Protože jsme vážně trvat zpětné vazby od zákazníků. To vede velkou část co děláme.

* Pokud chcete provést návrh o tom, jak můžeme vylepšit sady Visual Studio, můžete to provést pomocí [poslat návrh](talk-to-us.md#i-want-to-make-a-suggestion-about-visual-studio-features) nástroj.

* Pokud dochází k zablokování, při selhání nebo jiné problémy s výkonem, můžete jednoduše sdílet kroky pro reprodukci a podpůrné soubory s námi pomocí [nahlásit problém](talk-to-us.md#i-want-to-report-a-problem-with-visual-studio) nástroj.

## <a name="see-also"></a>Viz také:

* [Zpráva k vydání verze Visual Studio 2019](/visualstudio/releases/2019/release-notes/)
* [Co je nového ve Visual Studio SDK. 2019](../extensibility/whats-new-visual-studio-2019-sdk.md)
* [Microsoft Connect(); 2018 conference](https://www.microsoft.com/connectevent)
* [Co je nového v sadě Visual Studio 2017](whats-new-visual-studio-2017.md)
