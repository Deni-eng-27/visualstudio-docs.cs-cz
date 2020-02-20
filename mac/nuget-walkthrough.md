---
title: Zahrnutí balíčku NuGet do projektu
description: Tento dokument popisuje, jak zahrnout balíček NuGet do projektu pomocí Visual Studio pro Mac. Provede vás tím, že najde a stáhne balíček a také zavádí funkce integrace IDE.
author: jmatthiesen
ms.author: jomatthi
ms.date: 11/01/2019
ms.assetid: 5C800815-0B13-4B27-B017-95FCEF1A0EA2
ms.custom: conceptual
ms.openlocfilehash: 4200f466c079247d3efa036f4f7cca2fd2d6b5d2
ms.sourcegitcommit: bbff780cda82bb64862d77fe8f407f1803beb876
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/16/2019
ms.locfileid: "74127241"
---
# <a name="install-and-manage-nuget-packages-in-visual-studio-for-mac"></a>Instalace a Správa balíčků NuGet v Visual Studio pro Mac

Uživatelské rozhraní Správce balíčků NuGet v Visual Studio pro Mac umožňuje snadno nainstalovat, odinstalovat a aktualizovat balíčky NuGet v projektech a řešeních. Balíčky můžete vyhledat a přidat do projektů .NET Core, ASP.NET Core a Xamarin.

Tento článek popisuje, jak zahrnout balíček NuGet do projektu a demonstruje řetěz nástrojů, který tento proces způsobuje bez problémů.

Úvod k použití NuGet v Visual Studio pro Mac najdete v tématu [rychlý Start: instalace a použití balíčku v Visual Studio pro Mac](/nuget/quickstart/install-and-use-a-package-in-visual-studio-mac)

## <a name="find-and-install-a-package"></a>Vyhledání a instalace balíčku

1. Otevřete-li projekt v Visual Studio pro Mac, klikněte pravým tlačítkem myši na složku **závislosti** (složka**balíčky** , pokud používáte projekt Xamarin) v **oblast řešení** a vyberte možnost **Spravovat balíčky NuGet...** .

    ![Akce kontextu přidání nového balíčku NuGet](media/nuget-walkthrough-packages-menu.png)

2. Tím se spustí okno **Spravovat balíčky NuGet** . Ujistěte se, že rozevírací seznam zdroj v levém horním rohu dialogového okna je nastaven na `nuget.org`, takže prohledáváte úložiště balíčků centrálního NuGet.

    ![Výpis balíčků NuGet](media/nuget-walkthrough-add-packages1.png)

3. Pomocí vyhledávacího pole v pravém horním rohu Najděte konkrétní balíček, například `EntityFramework`. Po nalezení balíčku, který chcete použít, ho vyberte a kliknutím na tlačítko **Přidat balíček** zahajte instalaci.

    ![Přidat balíček NuGet EntityFramework](media/nuget-walkthrough-add-packages2.png)

4. Po stažení balíčku se do projektu přidá. Řešení se změní v závislosti na typu projektu, který upravujete:

    **Projekty Xamarin**
    * Uzel **odkazy** bude obsahovat seznam všech sestavení, která jsou součástí balíčku NuGet.
    * Uzel **balíčky** zobrazí každý balíček NuGet, který jste stáhli. Balíček můžete aktualizovat nebo odebrat z tohoto seznamu.
    
    **Projekty .NET Core**

    * Uzel **nuget > Node NuGet** zobrazí každý balíček NuGet, který jste stáhli. Balíček můžete aktualizovat nebo odebrat z tohoto seznamu.

## <a name="using-nuget-packages"></a>Používání balíčků NuGet

Po přidání balíčku NuGet a aktualizace odkazů na projekt můžete programovat s rozhraními API stejně jako v případě jakýchkoli odkazů na projekt.

Zajistěte, abyste do horní části souboru přidali všechny požadované direktivy `using`:

```csharp
using Newtonsoft.Json;
```

<a name="Package_Updates" class="injected"></a>

## <a name="updating-packages"></a>Aktualizace balíčků

Aktualizace balíčků lze provést buď najednou, kliknutím pravým tlačítkem myši na uzel **závislosti** (uzel**balíčky** pro projekty Xamarin) nebo jednotlivě na každém balíčku. Když je k dispozici nová verze balíčku NuGet, zobrazí se ikona aktualizace ![šipka nahoru s](media/nuget-walkthrough-update-icon.png)em kroužku.

Kliknutím pravým tlačítkem na **závislosti** přistupujete k kontextové nabídce a kliknutím na **aktualizovat** aktualizujte všechny balíčky:

![Nabídka balíčky](media/nuget-walkthrough-packages-menu-update.png)

* **Spravovat balíčky NuGet** – otevře okno pro přidání dalších balíčků do projektu.
* **Aktualizace** – zkontroluje zdrojový server pro každý balíček a stáhne všechny novější verze.
* **Obnovit** – stáhne všechny chybějící balíčky (bez aktualizace existujících balíčků na novější verze).

Možnosti aktualizace a obnovení jsou také k dispozici na úrovni řešení a mají vliv na všechny projekty v řešení.

### <a name="locating-outdated-packages"></a>Hledání zastaralých balíčků
Z panelu řešení můžete zobrazit aktuálně nainstalovanou verzi balíčku a kliknutím pravým tlačítkem na balíček aktualizovat.

![Nabídka balíčky s možnostmi aktualizace, odebrání a aktualizace](media/nuget-walkthrough-PackageMenu.png)

V případě, že je k dispozici nová verze balíčku, se zobrazí také oznámení vedle názvu balíčku, takže se můžete rozhodnout, jestli ho budete chtít aktualizovat.

![Oznámení zobrazené v případě, že je k dispozici nová verze balíčku](media/nuget-walkthrough-package-update-available.png)

V zobrazené nabídce máte dvě možnosti:

* **Aktualizace** – zkontroluje zdrojový server a stáhne novější verzi (pokud existuje).
* **Odebrat** – odebere balíček z tohoto projektu a odebere příslušná sestavení z odkazů projektu.

## <a name="manage-packages-for-the-solution"></a>Spravovat balíčky pro řešení

Správa balíčků pro řešení je pohodlný způsob práce s více projekty současně.

1. Klikněte pravým tlačítkem na řešení a vyberte **Spravovat balíčky NuGet...** :

    ![Spravovat balíčky NuGet pro řešení](media/nuget-walkthrough-manage-packages-solution.png)

1. Při správě balíčků pro řešení vám uživatelské rozhraní umožní vybrat projekty, které jsou ovlivněné operacemi:

    ![Selektor projektu při správě balíčků pro řešení](media/nuget-walkthrough-add-to-projects.png)

### <a name="consolidate-tab"></a>Karta konsolidovat

Když pracujete v řešení s více projekty, považuje se za osvědčený postup, abyste se ujistili, že kdekoli použijete stejný balíček NuGet v každém projektu, ale také použijete stejné číslo verze tohoto balíčku. Visual Studio pro Mac to usnadňuje tím, že poskytuje kartu **konsolidace** v uživatelském rozhraní Správce balíčků, když se rozhodnete spravovat balíčky pro řešení. Pomocí této karty můžete snadno zobrazit, kde jsou balíčky s různými čísly verzí používány různými projekty v řešení:

![Karta konsolidace uživatelského rozhraní Správce balíčků](media/nuget-walkthrough-consolidate-tab.png)

V tomto příkladu projekt NuGetDemo používá Microsoft. EntityFrameworkCore 2,20, zatímco NuGetDemo. Shared používá Microsoft. EntityFrameworkCore 2.2.6. Chcete-li konsolidovat verze balíčků, postupujte následovně:

- Vyberte projekty, které chcete aktualizovat v seznamu projektu.
- Vyberte verzi, kterou chcete použít ve všech těchto projektech v seznamu **Nová verze** , například Microsoft. EntityFrameworkCore 3.0.0.
- Klikněte na tlačítko **konsolidovat balíček** .

Správce balíčků nainstaluje vybranou verzi balíčku do všech vybraných projektů, po kterém se balíček už nebude zobrazovat na kartě **konsolidace** .

## <a name="adding-package-sources"></a>Přidávání zdrojů balíčků

Balíčky dostupné pro instalaci se zpočátku načítají z nuget.org. Do Visual Studio pro Mac však můžete přidat další umístění balíčků. To může být užitečné při testování vlastních balíčků NuGet ve vývoji nebo při používání privátního serveru NuGet v rámci vaší společnosti nebo organizace.

V Visual Studio pro Mac přejděte do části **Visual Studio > předvolby > > zdrojů NuGet** , abyste mohli zobrazit a upravit seznam zdrojů balíčků. Všimněte si, že zdrojem může být vzdálený server (určený adresou URL) nebo místní adresář.

![Zdroje balíčků](media/nuget-walkthrough-PackageSource.png)

Klikněte na tlačítko **Přidat** a nastavte nový zdroj. Zadejte popisný název a adresu URL (nebo cestu k souboru) do zdroje balíčku. Pokud je zdrojem zabezpečený webový server, zadejte taky uživatelské jméno a heslo. jinak ponechte prázdné tyto položky:

![Přidat zdroje balíčků](media/nuget-walkthrough-PackageSource2.png)

Při hledání balíčků se pak dají vybrat různé zdroje:

![Přidat zdroje balíčků](media/nuget-walkthrough-PackageSource3.png)

## <a name="version-control"></a>Správa verzí

Dokumentace k NuGet popisuje [použití NuGet bez potvrzení balíčků do správy zdrojových kódů](/nuget/consume-packages/packages-and-source-control). Pokud si nepřejete ukládat binární soubory a nepoužívané informace ve správě zdrojového kódu, můžete nakonfigurovat Visual Studio pro Mac pro automatické obnovení balíčků ze serveru. To znamená, že když vývojář poprvé načte projekt ze správy zdrojového kódu, Visual Studio pro Mac bude automaticky stahovat a instalovat požadované balíčky.

![Automaticky obnovit balíčky](media/nuget-walkthrough-AutoRestore.png)

Podrobnosti o tom, jak vyloučit `packages` adresář ze sledování, najdete v dokumentaci ke správě zdrojového kódu.

## <a name="related-video"></a>Související video

> [!Video https://channel9.msdn.com/Shows/Visual-Studio-Toolbox/Visual-Studio-for-Mac-Using-NuGet/player]

## <a name="see-also"></a>Viz také

* [Instalace a použití balíčku v aplikaci Visual Studio (v systému Windows)](/nuget/quickstart/install-and-use-a-package-in-visual-studio)
