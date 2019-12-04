---
title: Novinky v sadě Visual Studio 2019
titleSuffix: ''
description: Seznamte se s novými funkcemi v aplikaci Visual Studio 2019.
ms.date: 12/03/2019
helpviewer_keywords:
- Visual Studio, what's new
- what's new [Visual Studio]
ms.assetid: 00bec66b-bcee-46f5-91d9-f73a2b469744
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.prod: visual-studio-windows
ms.technology: vs-ide-general
ms.topic: conceptual
ms.workload:
- multiple
ms.openlocfilehash: eb4282941af9dff8619cb15510399b2e37e0c718
ms.sourcegitcommit: 00b71889bd72b6a566586885bdb982cfe807cf54
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/03/2019
ms.locfileid: "74777907"
---
# <a name="whats-new-in-visual-studio-2019"></a>Novinky v sadě Visual Studio 2019

**Aktualizováno pro [verzi 16,4](/visualstudio/releases/2019/release-notes/)**

>[!div class="button"]
>[Stáhněte si Visual Studio 2019](https://visualstudio.microsoft.com/downloads)

V rámci sady Visual Studio 2019 získáte špičkové nástroje a služby pro všechny vývojáře, aplikace a platformy. Bez ohledu na to, jestli používáte aplikaci Visual Studio poprvé nebo jste ji používali po dobu let, je v této nové verzi hodně podobné.

Tady je nejdůležitější rekapitulace, co je nového:

* **[Vývoj](#develop)** : zlepšení výkonu, okamžitého vyčištění kódu a lepších výsledků hledání díky lepšímu vývoji a produktivitě.
* **[Spolupráce](#collaborate)** : Využijte přirozenou spolupráci pomocí pracovního postupu Git-First, úpravy a ladění v reálném čase a revize kódu přímo v aplikaci Visual Studio.
* **[Ladění](#debug)** : zvýrazněte a přejděte na konkrétní hodnoty, optimalizujte využití paměti a proveďte automatické snímky provádění vaší aplikace.

Úplný seznam všeho, co je v této verzi nové, najdete v [poznámkách k verzi](/visualstudio/releases/2019/release-notes/).

## <a name="develop"></a>Vyvinout

Podívejte se na následující video, kde se dozvíte víc o tom, jak můžete ušetřit čas pomocí nových funkcí. <br><br>*Délka videa: 3,00 minut*

> [!VIDEO https://www.youtube.com/embed/n5sJ4EewKGk]

### <a name="improved-search"></a>Vylepšené vyhledávání

Dříve označované jako rychlé spuštění je naše nové vyhledávání rychlejší a efektivnější. Nyní se při psaní zobrazí výsledky hledání dynamicky. Výsledky hledání můžou často zahrnovat klávesové zkratky pro příkazy, takže je můžete snáze nepamatujíovat pro budoucí použití.

   ![Animace nového vyhledávacího prostředí v aplikaci Visual Studio 2019](media/vs-2019/new-search-feature.gif)

Nová logika přibližného vyhledávání bude najít cokoli, co potřebujete, bez ohledu na překlepy. To znamená, že pokud hledáte příkazy, nastavení, dokumentaci nebo jiné užitečné věci, nová funkce vyhledávání usnadňuje hledání, co hledáte.

### <a name="refactorings"></a>Refaktoringy

Existuje spousta nových a velmi užitečných refaktoringů C# , které usnadňují uspořádání kódu. Zobrazují se jako návrhy v žárovkě a zahrnují akce jako přesunutí členů do rozhraní nebo základní třídy, úpravy oborů názvů tak, aby odpovídaly struktuře složek, převedení smyček foreach na dotazy LINQ a další.

   ![Animace prostředí refaktoringu v aplikaci Visual Studio 2019](media/vs-2019/refactorings.gif)

Jednoduše volejte refaktoring stisknutím **kombinace kláves CTRL +.** a vyberte akci, kterou chcete provést.

### <a name="intellicode"></a>IntelliCode

[Visual Studio IntelliCode](/visualstudio/intellicode/) vylepšuje úsilí při vývoji softwaru pomocí umělé Intelligence (AI). IntelliCode vlaky napříč 2 000 open source projektů na GitHubu&mdash;každý s více než 100 hvězdiček&mdash;vygenerování doporučení.

![Animace IntelliCode ve Visual Studiu 2019](media/vs-2019/IntelliCode.gif)

Tady je několik způsobů, jak může Visual Studio IntelliCode přispět k lepší produktivitě:

* Doručovat dokončování kódu s ohledem na kontext
* Příručka pro vývojáře, aby dodržovala vzory a styly jejich týmu
* Hledání problémů s kódem, který se špatně zachytí
* Zaměřte se na revize kódu tím, že vykreslíte pozornost oblastí, které skutečně jsou

Původně jsme podporovali C# jenom v případě, že jsme IntelliCode jako rozšíření pro Visual Studio poprvé. **Novinka v 16,1**jsme přidali podporu pro C# a XAML "in-the-box". (Podpora pro C++ a TypeScript/JavaScript jsou ale pořád ve verzi Preview.)

A pokud používáte C#, Přidali jsme také možnost výuka vlastního modelu ve vlastním kódu.

Další informace o IntelliCode najdete v tématu popisujícím [obecnou dostupnost IntelliCode a také vás zajímá náhled](https://devblogs.microsoft.com/visualstudio/announcing-the-general-availability-of-intellicode-plus-a-sneak-peek/) a [Další kód. Posuňte se dál pomocí příspěvků Visual studia IntelliCode](https://devblogs.microsoft.com/visualstudio/code-more-scroll-less-with-visual-studio-intellicode/) na blogu.

### <a name="code-cleanup"></a>Vyčištění kódu

Párování s novým indikátorem stavu dokumentu je nový příkaz pro vyčištění kódu. Pomocí tohoto nového příkazu můžete identifikovat a opravit upozornění i návrhy kliknutím na tlačítko.

Vyčištění naformátuje kód a použije všechny opravy kódu navrhované [aktuálním nastavením](code-styles-and-code-cleanup.md) a [soubory. editorconfig](create-portable-custom-editor-options.md).

   ![Snímek obrazovky nového ovládacího prvku pro vyčištění kódu v aplikaci Visual Studio 2019](media/vs-2019/code-cleanup-profile.png)

Kolekce analyzérů můžete také ukládat jako profil. Například pokud máte malou sadu cílových analyzérů, kterou použijete často během kódu a pak máte další komplexní sadu analyzérů, která se má použít před revizí kódu, můžete nakonfigurovat profily pro řešení těchto různých úloh.

   ![Snímek obrazovky s ovládacím prvkem pro konfiguraci vyčištění kódu v aplikaci Visual Studio 2019](media/vs-2019/code-cleanup-profile-configure.png)

### <a name="per-monitor-aware-pma-rendering"></a>Vykreslování PMA (per-monitor)

Pokud používáte monitory, které jsou nakonfigurované s různými faktory měřítka zobrazení, nebo se vzdáleně připojit k počítači se zobrazenými faktory škálování, které se liší od vašeho hlavního zařízení, můžete si všimnout, že Visual Studio vypadá rozmazaný nebo vykreslený v nesprávném měřítku.

S vydáním sady Visual Studio 2019 provádíme aplikaci Visual Studio a PMA (per-monitor). Nyní se Visual Studio vykresluje správně bez ohledu na to, jaké faktory škálování displeje používáte.

   ![Vykreslování PMA (per-monitor) v aplikaci Visual Studio 2019](media/vs-2019/pma-dpi-scaling.png)

Další informace najdete v blogovém příspěvku o [lepším prostředí pro více monitorů v rámci sady Visual Studio 2019](https://devblogs.microsoft.com/visualstudio/a-better-multi-monitor-experience-with-visual-studio-2019/) .

### <a name="test-explorer"></a>Průzkumník testů

**Novinka v 16,2**: Aktualizovali jsme Průzkumníka testů, abychom zajistili lepší zacházení s velkými testovacími sadami, jednodušším filtrováním, více zjistitelnými příkazy, zobrazeními seznamu skladeb na kartách a přizpůsobitelnými sloupci, které vám umožní doladit informace o tom, jaké informace o testu se zobrazují.

   ![Snímek obrazovky, který zobrazuje vylepšení uživatelského rozhraní v Průzkumníku testů](media/vs-2019/test-explorer-ui.png)

### <a name="net-core"></a>.NET Core

**Novinka v 16,3**: zahrnuli jsme podporu pro .net Core 3,0. Pro různé platformy Open Source&mdash;a plně podporované Microsoftem.

Další informace najdete v příspěvku na blogu o [.NET Core 3,0](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-0/) .

## <a name="collaborate"></a>Spolupráce

Podívejte se na následující video, kde se dozvíte víc o tom, jak se dá tým seskupit a vyřešit problémy. <br><br>*Délka videa: 4,22 minut*

> [!VIDEO https://www.youtube.com/embed/dKLJsiK1QU8]

### <a name="cloud-first-workflow"></a>Cloud – první pracovní postup

Něco, co si všimnete při otevření sady Visual Studio 2019, je nové úvodní okno.

   ![Snímek obrazovky s novým oknem Start v aplikaci Visual Studio 2019](media/vs-2019/start-window-dark.png)

Okno Start nabízí několik možností, jak rychle získat kód. Umístili jsme možnost klonovat nebo rezervovat kód z úložiště, nejdřív.

   ![Animace prostředí Git-First v aplikaci Visual Studio 2019](media/vs-2019/git-first.gif)

Okno Start také obsahuje možnosti pro otevření projektu nebo řešení, otevření místní složky nebo vytvoření nového projektu.

Další informace najdete v tématu [získání kódu: jak jsme navrhli nový Blogový příspěvek pro úvodní okno sady Visual Studio](https://devblogs.microsoft.com/visualstudio/get-to-code-how-we-designed-the-new-visual-studio-start-window/) .

### <a name="live-share"></a>Live Share

[Visual Studio Live Share](https://visualstudio.microsoft.com/services/live-share/) je služba pro vývojáře, která umožňuje sdílet základ kódu a jeho kontext s společník a získat rychlou obousměrnou spolupráci přímo v rámci sady Visual Studio. Pomocí Live Share může společník číst, Procházet, upravovat a ladit projekt, který s nimi sdílíte, a dělat plynule a bezpečně.

A v rámci sady Visual Studio 2019 je tato služba nainstalována ve výchozím nastavení.

![Animace, která zobrazuje funkci Live Share spolupráci v aplikaci Visual Studio 2019](media/vs-2019/live-share.gif)

Další informace najdete v příspěvku na blogu [Visual Studio Live Share pro revize kódu v reálném čase a](https://devblogs.microsoft.com/visualstudio/visual-studio-live-share-for-real-time-code-reviews-and-interactive-education/) v příspěvku na blogu o interaktivním vzdělávání a v příspěvku na blogu [Live Share sady Visual Studio 2019](https://devblogs.microsoft.com/visualstudio/live-share-now-included-with-visual-studio-2019/) .

### <a name="integrated-code-reviews"></a>Integrované revize kódu

Zavádíme nové rozšíření, které můžete stáhnout pro použití se sadou Visual Studio 2019. S tímto novým rozšířením můžete kontrolovat, spouštět a dokonce ladit žádosti o přijetí změn od týmu bez nutnosti opustit Visual Studio. Podporujeme kód v úložištích GitHub a Azure DevOps.

   ![Snímek obrazovky s novým oknem Start v aplikaci Visual Studio 2019](media/vs-2019/pr-experience.png)

Další informace najdete v příspěvku na blogu o [revizích kódu pomocí rozšíření pro žádosti o získání dat v aplikaci Visual Studio](https://devblogs.microsoft.com/visualstudio/code-reviews-using-the-visual-studio-pull-requests-extension/) .

## <a name="debug"></a>Ladit

Podívejte se na následující video, kde se dozvíte víc o tom, jak můžete s přesným cílem v průběhu ladění vynulovat. <br><br>*Délka videa: 3,54 minut*

> [!VIDEO https://www.youtube.com/embed/hr72Fs8n_9c]

### <a name="performance-gains"></a>Nárůst výkonu

Převzali jsme všechny datové zarážky s jednou výhradním přístupem C++ a přizpůsobovat je pro aplikace .NET Core.

   ![Animace, která zobrazuje zarážky dat ladění v aplikaci Visual Studio 2019](media/vs-2019/debug-data-breakpoints.gif)

Takže pokud píšete v C++ rozhraní nebo .NET Core, mohou být datové zarážky dobrou alternativou pro pouhé umístění běžných zarážek. Datové zarážky jsou také skvělé pro scénáře, jako je například hledání, kde se v seznamu mění nebo přidávají nebo odebírají globální objekty.

A pokud jste C++ vývojář, který vyvíjí velké aplikace, sady Visual Studio 2019 převedly symboly mimo proces, což vám umožní ladit tyto aplikace bez potíží souvisejících s pamětí.

### <a name="search-while-debugging"></a>Hledat během ladění

Pravděpodobně jste to předtím, a to v okno Kukátko pro řetězec mezi sadou hodnot. V aplikaci Visual Studio 2019 jsme přidali hledání v oknech kukátko, místní hodnoty a automatické hodnoty, které vám pomůžou najít objekty a hodnoty, které hledáte.

   ![Animace, která zobrazuje okno hledání ladění v aplikaci Visual Studio 2019](media/vs-2019/debug-window-search.gif)

Můžete také formátovat, jak se hodnota zobrazuje v oknech kukátko, místní hodnoty a automatické hodnoty.  Dvakrát klikněte na jednu z položek v některém z oken a přidejte čárku (",") pro přístup k rozevíracímu seznamu možných specifikátorů formátu, z nichž každý obsahuje popis zamýšleného efektu.

   ![Funkce New okno Kukátko a Format Values v aplikaci Visual Studio 2019](media/search-watch-window.png)

Další informace najdete v tématu [Vylepšená v aplikaci Visual Studio 2019: hledání objektů a vlastností v příspěvku na blogu sledování, automatické hodnoty a místní hodnoty v systému Windows](https://devblogs.microsoft.com/visualstudio/enhanced-in-visual-studio-2019-search-for-objects-and-properties-in-the-watch-autos-and-locals-windows/) .

### <a name="snapshot-debugger"></a>Snapshot Debugger

Získejte snímek provádění vaší aplikace v cloudu, abyste viděli přesně to, co se děje. (Tato funkce je k dispozici pouze v Visual Studio Enterprise.)

   ![Animace, která zobrazuje Snapshot Debugger v aplikaci Visual Studio 2019 Enterprise](media/vs-2019/snapshot-debugger.gif)

Přidali jsme podporu pro cílení aplikací ASP.NET (základní a desktopové), které běží na virtuálním počítači Azure. A přidali jsme podporu pro aplikace, které běží ve službě Azure Kubernetes. Snapshot Debugger vám může výrazně zkrátit dobu potřebnou k vyřešení problémů, ke kterým dochází v produkčních prostředích.

Další informace najdete v článku [ladění živých ASP.NET aplikací Azure pomocí stránky Snapshot Debugger](../debugger/debug-live-azure-applications.md) a na blogovém příspěvku [pro Visual Studio Enterprise 2019 s časem zavedení](https://devblogs.microsoft.com/visualstudio/introducing-time-travel-debugging-for-visual-studio-enterprise-2019/) .

### <a name="microsoft-edge-insider-support"></a>Podpora prohlížeče Microsoft Edge Insider

**Novinka v 16,2**: můžete nastavit zarážku v aplikaci JavaScriptu a spustit ladicí relaci pomocí prohlížeče [Microsoft Edge Insider](https://www.microsoftedgeinsider.com/) . Když to uděláte, Visual Studio otevře nové okno prohlížeče s povoleným laděním, které pak můžete použít ke krokování v aplikaci JavaScript aplikace v sadě Visual Studio.

   ![Snímek obrazovky, který zobrazuje vykreslování kódu JavaScriptu v prohlížeči](media/vs-2019/edge-chromium-breakpoint.png)

### <a name="pinnable-properties-tool"></a>Nástroj Pinnable Properties

**Novinka v 16,4**: teď je snazší identifikovat objekty podle jejich vlastností při ladění pomocí nového nástroje Pinnable Properties. Stačí umístit ukazatel myši na vlastnost, kterou chcete zobrazit v okně ladicího programu okna Kukátko, automatické hodnoty a místní hodnoty, klikněte na ikonu připnutí a okamžitě zobrazte informace, které hledáte v horní části okna.

   ![Animace, která ukazuje, jak připnout vlastnosti v ladicím programu sady Visual Studio pomocí nástroje Pinnable Properties Tool](media/vs-2019/debugger-pinnable-properties.gif)

## <a name="whats-next"></a>Co dál

Visual Studio 2019 aktualizujeme často o nové funkce, které můžou zlepšit vývojové prostředí. Další informace o našich nejnovějších inovacích najdete v blogu sady [Visual Studio](https://devblogs.microsoft.com/visualstudio/). A pro záznam toho, co jsme vydali v předběžné verzi Preview, se podívejte na poznámky k [verzi Preview](/visualstudio/releases/2019/release-notes-preview/).

Chcete získat další informace o tom, co je jinde v sadě Works for Visual Studio 2019? Podívejte se na [plán sady Visual Studio](/visualstudio/productinfo/vs-roadmap/).

## <a name="give-us-feedback"></a>Sdělte nám svůj názor

Proč odeslat zpětnou vazbu týmu sady Visual Studio? Vzhledem k tomu, že povedeme zpětnou vazbu zákazníků. To zahrnuje mnoho toho, co máme.

* Pokud si chcete udělat nějaký návrh, jak můžeme vylepšit aplikaci Visual Studio, můžete k tomu použít nástroj [navrhnout funkci](suggest-a-feature.md) .

* Pokud dojde k zablokování, zhroucení nebo jinému problému s výkonem, můžete snadno sdílet kroky reprodukci a podpůrné soubory s námi pomocí nástroje [nahlásit problém](how-to-report-a-problem-with-visual-studio.md) .

## <a name="see-also"></a>Viz také:

* [Zpráva k vydání verze pro Visual Studio 2019](/visualstudio/releases/2019/release-notes/)
* [Co je nového v sadě Visual Studio 2019 SDK](../extensibility/whats-new-visual-studio-2019-sdk.md)
* [Zpráva k vydání verze pro Visual Studio 2019 for Mac](/visualstudio/releasenotes/vs2019-mac-relnotes/)
* [Konference k Microsoft Build 2019](https://www.microsoft.com/build)
* [Microsoft Connect (); konference 2018](https://www.microsoft.com/connectevent)
