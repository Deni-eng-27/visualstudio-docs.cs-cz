---
title: Visual Studio for Mac Tour
description: Visual Studio for Mac obsahuje integrované vývojové prostředí pro vytváření aplikací .NET v systému macOS, včetně webů ASP.NET Core a projekty Xamarin pro iOS, Android, Mac a Xamarin.Forms.
author: conceptdev
ms.author: crdun
ms.date: 11/03/2018
ms.assetid: 7DC64A52-AA41-4F3A-A8A1-8A20BCD81CC7
ms.openlocfilehash: 99ad6cfcda7bf271853aff5c095bbb0664b3b592
ms.sourcegitcommit: 5a65ca6688a2ebb36564657d2d73c4b4f2d15c34
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/15/2019
ms.locfileid: "54316172"
---
# <a name="visual-studio-2017-for-mac-tour"></a>Visual Studio 2017 for Mac Tour

Visual Studio pro Mac vyvíjí Xamarinu pro zaměřené na mobilní zařízení IDE, Xamarin Studio, mobilní a cloudové vývojové prostředí na počítači Mac. Tento nástroj určený pro vývojáře můžete využít k vytváření aplikací pro všechny platformy musí vaši uživatelé rozhraní .NET.

Uživatelské rozhraní (UX sady Visual Studio for Mac) je podobná jeho protějšek Windows, ale s nativní macOS chování. Vytvoření, otevření nebo vyvíjet aplikace bude známým všem uživatelům, kteří dříve používali Visual Studio na Windows. Kromě toho Visual Studio for Mac využívá mnoho výkonných nástrojů, které usnadňují jeho protějšek Windows výkonné IDE. Platforma kompilátor Roslyn se používá pro refaktoring a technologii IntelliSense. Jeho modul systému a sestavení projektu pomocí nástroje MSBuild a jeho Editor zdrojového kódu podporuje sady TextMate. Používá stejný ladicím modulem pro aplikace Xamarin a .NET Core a stejného návrháře pro Xamarin.iOS a Xamarin.Android.

Tento článek se věnuje různých oddílů sady Visual Studio pro Mac, poskytuje pohled na některé z funkcí, které usnadňují výkonný nástroj pro vytváření aplikací pro víc platforem.

## <a name="ide-tour"></a>Prohlídka integrovaného vývojového prostředí

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

## <a name="see-also"></a>Viz také:

- [Visual Studio IDE (on Windows)](/visualstudio/ide/visual-studio-ide)