---
title: 'Rychlý start: Vytvoření webové služby ASP.NET Core vF#'
description: Zjistěte, jak vytvořit webovou službu ASP.NET Core v sadě Visual Studio s F#, krok za krokem.
ms.date: 08/24/2018
ms.topic: quickstart
author: cartermp
ms.author: phcart
manager: andrehal
dev_langs:
- FSharp
ms.workload:
- aspnet
- dotnetcore
ms.openlocfilehash: b4b6a9bcc9828d0fdeb76f3f74732d8d5496e59c
ms.sourcegitcommit: 4ffb7be5384ad566ce46538032bf8561754c61a4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/15/2019
ms.locfileid: "58069759"
---
# <a name="quickstart-use-visual-studio-to-create-your-first-aspnet-core-web-service-in-f"></a>Rychlý start: Pomocí sady Visual Studio k vytvoření vaší první webové služby ASP.NET Core v F\#

V tomto úvodu 5 až 10 minut na F# v sadě Visual Studio vytvoříte F# webová aplikace ASP.NET Core.

Pokud jste ještě nenainstalovali aplikaci Visual Studio, přejděte [soubory ke stažení Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) stránku a nainstalovat zdarma.

## <a name="create-a-project"></a>Vytvoření projektu

Nejprve vytvoříte projekt webového rozhraní API ASP.NET Core. Typ projektu je součástí souborů šablon, které tvoří funkční webovou službu, než jste přidali ještě nic!

::: moniker range="vs-2017"

1. Otevřít Visual Studio.

2. V horní nabídce zvolte **souboru** > **nový** > **projektu**.

3. V **nový projekt** dialogové okno, v levém podokně rozbalte **Visual F#** , klikněte na tlačítko **webové**. V prostředním podokně vyberte **webové aplikace ASP.NET Core**, klikněte na tlačítko **OK**.

     Pokud se nezobrazí **.NET Core** kategorii šablony projektu, zvolte **otevřít instalační program Visual Studio** odkaz v levém podokně. Spustí se instalační program pro Visual Studio. Zvolte **vývoj pro ASP.NET a web** úloh, klikněte na tlačítko **změnit**.

     ![Úlohy technologie ASP.NET v instalačním programu VS](../ide/media/quickstart-aspnet-workload.png)

4 ve **nová webová aplikace ASP.NET Core** dialogu **ASP.NET Core 2.1** z hlavní nabídky rozevíracího seznamu. (Pokud se nezobrazí **ASP.NET Core 2.1** v seznamu, nainstalujte ji pomocí následujících **Stáhnout** odkaz, který by se měla objevit v žlutý pruh v horní části dialogu.) Zvolte **OK**.

::: moniker-end

::: moniker range=">=vs-2019"

1. Otevřít Visual Studio.

2. V okně Start zvolte **vytvořte nový projekt**.

3. Na **vytvořte nový projekt** zadejte **f # webové** do vyhledávacího pole a klikněte na tlačítko **webové aplikace ASP.NET Core** šablony projektu. Zvolte **Další**.

4. Na **konfigurovat nový projekt** stránky, zadejte název a klikněte na tlačítko **vytvořit**.

5. Na **vytvořit novou webovou aplikaci ASP.NET Core** stránce **ASP.NET Core 2.1** z hlavní nabídky rozevíracího seznamu a klikněte na tlačítko **vytvořit**.

::: moniker-end

## <a name="explore-the-ide"></a>Prozkoumejte rozhraní IDE

1. V **Průzkumníka řešení** nástrojů, rozbalte **řadiče** složky, klikněte na tlačítko **ValuesController.fs** ho otevřete v editoru.

   ![Průzkumník řešení se složkou řadiče rozbalení v F# projekt webového rozhraní API](../ide/media/hello-world-fs-sln-explorer.png)

2. V dalším kroku změnit `Get()` člen bude následující:

   ```fsharp
   [<HttpGet>]
   member this.Get() =
       let values = [|"Hello"; "World"; "First F#/ASP.NET Core web API!"|]
       ActionResult<string[]>(values)
   ```

Kód je jednoduché. F# Pole hodnot je vázán na `values` název a potom předá do rozhraní ASP.NET Core MVC jako `ActionResult`. ASP.NET Core se postará o zbytek za vás.

V editoru, by měl vypadat jako tento:

![Upravené člen Get](../ide/media/hello-world-fs-get-member.png)

## <a name="run-the-application"></a>Spuštění aplikace

1. Stisknutím klávesy **Ctrl**+**F5** ke spuštění aplikace a otevřete ho ve webovém prohlížeči.

2. Na stránce by měl přejít na `/api/values` trasy, ale pokud tomu tak není, zadejte `https://localhost:44396/api/values` do prohlížeče.

Webový prohlížeč se teď budou zobrazovat JSON odpovídající jste zadali dříve.

## <a name="next-steps"></a>Další kroky

Blahopřejeme k dokončení tohoto rychlého startu! Věříme, že jste se dozvěděli něco o F#, ASP.NET Core a integrovaném vývojovém prostředí sady Visual Studio. Pokud chcete zobrazit aplikaci spuštěnou na veřejný server, vyberte na následující tlačítko.

> [!div class="nextstepaction"]
> [Nasaďte aplikaci do služby Azure App Service](../deployment/quickstart-deploy-to-azure.md)

Další informace o F#, projděte si oficiální [ F# průvodce](/dotnet/fsharp/index).