---
title: Visual Studio for Mac Tour
description: Visual Studio for Mac obsahuje integrované vývojové prostředí pro vytváření aplikací .NET v systému macOS, včetně webů ASP.NET Core a projekty Xamarin pro iOS, Android, Mac a Xamarin.Forms.
author: conceptdev
ms.author: crdun
ms.date: 02/07/2019
ms.assetid: 7DC64A52-AA41-4F3A-A8A1-8A20BCD81CC7
ms.custom: video
ms.openlocfilehash: 43b7918dfba6ff1d8076d3173900ecdc1b1223a3
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/17/2019
ms.locfileid: "59655774"
---
# <a name="visual-studio-2017-for-mac-tour"></a>Visual Studio 2017 for Mac tour

> [!NOTE]
> 2019 Visual Studio for Mac je [nyní k dispozici](installation.md).

Visual Studio for Mac je .NET _integrovaného vývojového prostředí_ na počítači Mac, který je možné upravit, ladit a vytvářet kód a pak publikujete aplikaci. Kromě očekávané funkce, jako je standardní editor a ladicí program Visual Studio for Mac obsahuje kompilátory, nástroje dokončování kódu, grafičtí návrháři pro a správy zdrojového kódu do úložiště ese proces vývoje softwaru.

Visual Studio for Mac podporuje mnoho stejné typy souborů jako jeho protějšek Windows, například `.csproj`, `.fsproj`, nebo `.sln` soubory a podporuje funkce, jako je například EditorConfig, což znamená, že můžete použít rozhraní IDE, který vám bude nejlépe vyhovovat.
Vytvoření, otevření nebo vyvíjet aplikace bude známým všem uživatelům, kteří dříve používali Visual Studio na Windows. Kromě toho Visual Studio for Mac využívá mnoho výkonných nástrojů, které usnadňují jeho protějšek Windows výkonné IDE. Platforma kompilátor Roslyn se používá pro refaktoring a technologii IntelliSense. Jeho modul systému a sestavení projektu pomocí nástroje MSBuild a jeho Editor zdrojového kódu podporuje sady TextMate. Používá stejný ladicím modulem pro aplikace Xamarin a .NET Core a stejného návrháře pro Xamarin.iOS a Xamarin.Android.

## <a name="what-can-i-do-in-visual-studio-for-mac"></a>Co můžu dělat v sadě Visual Studio for Mac

Visual Studio for Mac podporuje následující typy vývoje pro:

- Webové aplikace ASP.NET Core s C#, F#a podpora pro stránky Razor, JavaScript a TypeScript
- Konzolové aplikace .NET core s C# neboF#
- Hry Unity pro různé platformy a aplikace sC#
- Aplikace pro Android, iOS, tvOS a watchOS v Xamarinu s C# nebo F# a XAML
- Desktopové aplikace cocoa v C# neboF#

Tento článek se věnuje různých oddílů sady Visual Studio pro Mac, poskytuje pohled na některé z funkcí, které usnadňují výkonný nástroj pro vytváření těchto aplikací.

## <a name="ide-tour"></a>Prohlídka integrovaného vývojového prostředí (IDE)

Visual Studio for Mac je uspořádaný do několika oddílů pro správu souborů aplikace a nastavení, vytvoření kódu aplikace a ladění.

## <a name="welcome-screen"></a>Úvodní obrazovka

Při spuštění, zobrazí Visual Studio pro Mac *úvodní obrazovka*:

![Úvodní obrazovka](media/ide-tour-image1.png)

Na úvodní obrazovce obsahuje následující části:

- **Panel nástrojů** – poskytuje rychlý přístup k panelu hledání. Při načítání řešení, panelu nástrojů se používá k nastavení konfigurace aplikací pro ladění a pro zobrazování chyb.
- **Začínáme se službou** – poskytuje rychlý přístup k užitečným tématům pro vývojáře, Začínáme se sadou Visual Studio pro Mac.
- **Poslední řešení** – poskytuje rychlý přístup k naposledy otevřeným řešení, jakož i praktické tlačítka pro otevření nebo vytvoření projektů.
- **Novinky pro vývojáře** – informační kanál, který udržuje je aktuální na nejnovější informace o Microsoft Developer.

## <a name="solutions-and-projects"></a>Řešení a projekty

Následující obrázek ukazuje Visual Studio for Mac pomocí aplikace načíst:

![Načtení sady Visual Studio pro Mac s aplikací](media/ide-tour-image17.png)

Následující části obsahují základní informace o hlavních oblastech v sadě Visual Studio pro Mac.

## <a name="solution-pad"></a>Oblasti řešení

Oblasti řešení Uspořádá projekty v řešení:

![Projekty, které jsou uspořádány v oblasti řešení](media/ide-tour-image18.png)

Je to, kde soubory pro zdrojový kód, prostředky, uživatelské rozhraní a závislosti jsou uspořádány do projektů specifické pro platformu.

Další informace o použití projekty a řešení v sadě Visual Studio pro Mac, najdete v článku [projekty a řešení](/visualstudio/mac/projects-and-solutions) článku.

## <a name="assembly-references"></a>Odkazy na sestavení

Odkazy na sestavení pro každý projekt jsou k dispozici ve složce odkazy:

![Složka s odkazy v oblasti řešení](media/ide-tour-image19.png)

Další odkazy jsou přidána pomocí **upravit odkazy** dialogové okno, které se zobrazí na něj poklikejte na složku odkazy nebo tak, že vyberete **upravit odkazy** na jeho místní nabídky akce:

![Odkazy na dialogové okno Upravit](media/ide-tour-image20.png)

Další informace o používání odkazů v sadě Visual Studio pro Mac, najdete v článku [Správa odkazů v projektu](/visualstudio/mac/managing-references-in-a-project) článku.

## <a name="dependencies--packages"></a>Závislosti / balíčky

Všechny externí závislosti používaných v aplikaci jsou uloženy ve složce závislosti nebo balíčky, v závislosti na tom, jestli jste v.Net Core nebo Xamarin.iOS/Xamarin.Android projektu. Ty se obvykle poskytují ve formě NuGet.

Správce balíčků NuGet je nejoblíbenější Správce balíčků pro vývoj na platformě .NET. Díky podpoře NuGet sady Visual Studio můžete snadno vyhledat a přidat balíčky do vašeho projektu do aplikace.

Chcete-li přidat závislost pro vaši aplikaci, klikněte pravým tlačítkem na závislosti / balíčky a pak zvolte položku **přidat balíčky**:

![Přidání balíčku NuGet](media/ide-tour-image21.png)

Informace o použití balíčku NuGet v aplikaci najdete v [projektu včetně NuGet ve vašem projektu](/visualstudio/mac/nuget-walkthrough) článku.

## <a name="refactoring"></a>Refaktoring

Visual Studio for Mac obsahuje dva užitečné způsoby, jak kód Refaktorovat: Kontext akce a zdrojová analýza. Další informace o nich v [refaktoringu](/visualstudio/mac/refactoring) článku.

## <a name="debugging"></a>Ladění

Visual Studio for Mac obsahuje nativní ladicí program umožňuje ladění podporu pro aplikace Xamarin.Android, Xamarin.iOS a Xamarin.Mac. Visual Studio pro Mac používá Mono Obnovitelně ladicí program, který je implementován do modulu Mono runtime, umožňuje rozhraní IDE k ladění spravovaného kódu na všech platformách. Další informace o ladění, najdete [ladění](/visualstudio/mac/debugging) článku.

Ladicí program obsahuje bohatou vizualizéry pro speciální typy, jako jsou řetězce, barvy, adresy URL, jakož i velikostí, souřadnice a Bézierovy křivky.

Další informace o datové vizualizace ladicího programu, najdete [vizualizace dat](/visualstudio/mac/data-visualizations) článku.

## <a name="version-control"></a>Správa verzí

Visual Studio pro Mac se integruje s systémy správy zdrojového kódu Git a Subversion. Projekty v rámci správy zdrojového kódu, jsou označeny větev uvedená vedle názvu řešení:

![Název větve k označení projekt pod správou zdrojových kódů](media/ide-tour-image22.png)

Soubory s nepotvrzené změny mít anotaci na jejich ikonami v podokně řešení, jak je znázorněno na následujícím obrázku:

![Nepotvrzené soubory v oblasti řešení](media/ide-tour-image23.png)

Další informace o používání správy verzí v sadě Visual Studio, najdete v článku [verzí](/visualstudio/mac/version-control) článku.

## <a name="related-video"></a>Související videa

> [!Video https://channel9.msdn.com/Shows/Visual-Studio-Toolbox/Visual-Studio-for-Mac-Overview/player]

## <a name="see-also"></a>Viz také:

- [Visual Studio IDE (on Windows)](/visualstudio/ide/visual-studio-ide)
