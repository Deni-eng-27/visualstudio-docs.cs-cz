---
title: Použijte sadu Visual Studio k vytvoření webové aplikace ASP.NET Core v jazyce C#
description: Naučte se vytvářet webové aplikace ASP.NET Core v sadě Visual Studio pomocí C#, krok za krokem.
ms.custom: mvc
ms.date: 06/27/2018
ms.prod: visual-studio-dev15
ms.technology: vs-acquisition
ms.topic: quickstart
author: TerryGLee
ms.author: tglee
manager: douge
dev_langs:
- CSharp
ms.workload:
- aspnet
- dotnetcore
ms.openlocfilehash: 9d8aa6a6147ff57ba72f1cc69240ef5a7137cd73
ms.sourcegitcommit: e9d1018a01af62c3dc5aeb6b325faba7e20bd496
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/28/2018
ms.locfileid: "37089296"
---
# <a name="quickstart-use-visual-studio-to-create-your-first-aspnet-core-web-app"></a>Rychlý úvod: Použití Visual Studio k vytvoření první webové aplikace ASP.NET Core

V tento úvod 5 až 10 minut v sadě Visual Studio integrované vývojové prostředí (IDE) vytvoříte jednoduchou webovou aplikaci ASP.NET Core C#.

Pokud jste ještě nenainstalovali Visual Studio, přejděte k [Visual Studio stáhne](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) stránky instalaci zdarma.

## <a name="create-a-project"></a>Vytvoření projektu

Nejdřív vytvoříte projekt webové aplikace technologie ASP.NET Core. Typ projektu se dodává s soubory šablon, které tvoří funkční webovou aplikaci, než jste přidali i nic!

1. Otevřete Visual Studio 2017.

1. V horním řádku nabídek zvolte **Soubor** > **Nový** > **Projekt**.

1. V **nový projekt** dialogové okno, v levém podokně rozbalte **Visual C#**, zvolte **.NET Core**. V prostředním podokně vyberte **webové aplikace ASP.NET Core**, zvolte **OK**.

     Pokud nevidíte **.NET Core** projektu kategorie šablony, vyberte **otevřete instalační program Visual Studio** odkaz v levém podokně. Spustí se instalační program pro Visual Studio. Vyberte **ASP.NET a webové vývoj** zatížení, zvolte **upravit**.

     ![Zatížení technologie ASP.NET v instalační program VS](../ide/media/quickstart-aspnet-workload.png)

1. V **nové webové aplikace ASP.NET Core** dialogové okno, vyberte **technologii ASP.NET 2.0 základní** v hlavní nabídce rozevíracího seznamu. (Pokud nevidíte **technologii ASP.NET 2.0 základní** v seznamu, nainstalujte ji podle **Stáhnout** odkaz, který by se měla objevit v žlutý pruh v horní části dialogové okno.) Zvolte **OK**.

   ![Dialogové okno nové webové aplikace ASP.NET Core](../ide/media/quickstart-aspnet-core20.png)

## <a name="explore-the-ide"></a>Prozkoumejte rozhraní IDE

1. V **Průzkumníku řešení** nástrojů, rozbalte **stránky** složku, pak zvolte **About.cshtml** a otevře se v editoru. Tento soubor odpovídá stránku s názvem **o** ve webové aplikaci.

1. V editoru, zvolte `AboutModel` a potom stiskněte klávesu **F12** nebo zvolte **přejít k definici** z nabídky kontextu (klikněte pravým tlačítkem). Tento příkaz má definici `AboutModel` třída jazyka C#.

   ![Přejít k definici kontextové nabídky](../ide/media/quickstart-aspnet-gotodefinition.png)

1. Další vyčištění `using` direktivy v horní části souboru pomocí jednoduchého zástupce. Vybrat kteroukoli z zašedlá pomocí direktiv a [rychlé akce](../ide/quick-actions.md) žárovky se zobrazí pod vsuvka nebo na levém okraji. Zvolte žárovky a potom vyberte **odeberte nepotřebné direktiv Using**.

     Nepotřebné direktiv Using se odstraní ze souboru.

1. V `OnGet()` metoda, změňte obsah pro následující kód:

 ```csharp
 public void OnGet()
 {
     string directory = Environment.CurrentDirectory;
     Message = String.Format("Your directory is {0}.", directory);
 }
 ```

1. Uvidíte dvě podtržení vlnovkami vyskytovat v části **prostředí** a **řetězec**, protože tyto typy nejsou v oboru. Otevřete **seznam chyb** nezobrazí nástrojů najdete v části stejné chyby. (Pokud se nezobrazí **seznam chyb** nástrojů vyberte **zobrazení** > **seznam chyb** z hlavní nabídky panelu.)

   ![Seznam chyb](../ide/media/quickstart-aspnet-errorlist.png)

1. V okně editoru umístěte kurzor na buď řádek, který obsahuje chybu, a potom vyberte žárovky rychlé akce na levém okraji. Z rozevírací nabídky vyberte **pomocí systému;** na začátek souboru přidejte tato direktiva a případné chyby opravte.

## <a name="run-the-application"></a>Spuštění aplikace

1. Stiskněte klávesu **Ctrl**+**F5** otevřete ve webovém prohlížeči a spusťte aplikaci.

1. V horní části webu, zvolte **o** zobrazíte zprávy jste přidali v adresáři `OnGet()` metodu pro **o** stránky.

1. Zavřete webový prohlížeč.

> [!NOTE]
> Pokud se zobrazí chybová zpráva, která uvádí, že **nebylo možné se připojit k webovému serveru služby IIS Express**, zavřete Visual Studio a otevřete jej pomocí **spustit jako správce** možnost v nabídce klikněte pravým tlačítkem nebo kontextu. Pak spusťte aplikaci znovu.

Blahopřejeme k dokončení tento rychlý start! Věříme, že jste se naučili chvíli o prostředí Visual Studio IDE. Pokud chcete pustíte hlubší do jeho možnosti, pokračujte prosím se v kurzu **kurzy** části obsahu.

## <a name="next-steps"></a>Další kroky

Blahopřejeme k dokončení tento rychlý start! Věříme, že jste se dozvěděli, chvíli o C#, ASP.NET Core a Visual Studio IDE. Pokud chcete zobrazit aplikaci spuštěnou na veřejný server, vyberte na následující tlačítko.

> [!div class="nextstepaction"]
> [Nasazení aplikace do Azure App Service](..//deployment/quickstart-deploy-to-azure.md)

Další informace, pokračujte kurzy, [začít pracovat s C# a ASP.NET v sadě Visual Studio](tutorial-csharp-aspnet-core.md) a [Začínáme s ASP.NET MVC jádra a sady Visual Studio](/aspnet/core/tutorials/first-mvc-app/start-mvc?tabs=aspnetcore2x).
