---
title: Prohlídka funkce nasazení
description: Další informace o možnostech pro nasazení aplikací ze sady Visual Studio.
ms.custom: mvc
ms.date: 11/26/2017
ms.technology: vs-ide-deployment
ms.topic: quickstart
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- .NET applications, deploying
- components [Visual Studio], deploying
- installers
- publishing
- deploying applications [Visual Studio]
- deploying applications [Visual Studio], about deploying applications
- components [.NET Framework], deploying
ms.assetid: 63fcdd5b-2e54-4210-9038-65bc23167725
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e301131afc62b0564ca302adb9a079b42b52c5f8
ms.sourcegitcommit: f685fa5e2df9dc307bf1230dd9dc3288aaa408b5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/19/2018
ms.locfileid: "36234683"
---
# <a name="quickstart-first-look-at-deployment-in-visual-studio"></a>Rychlý úvod: První pohled na nasazení v sadě Visual Studio

Nasazením aplikace, služby nebo komponenty ji budete distribuovat pro instalaci na dalších počítačích, zařízeních, serverech nebo v cloudu. V sadě Visual Studio můžete zvolit vhodnou metodu pro potřebný typ nasazení. (Mnoho typů aplikací podporují jiné nástroje nasazení jako je například nasazení příkazového řádku nebo NuGet, které nejsou tady popsané).

Najdete podrobné pokyny pro podrobné pokyny. Pokud nasazujete webovou aplikaci a potřebujete podrobnější informace k rozhodování o na nejlepší možnost nasazení ze sady Visual Studio, najdete v části [jaké možnosti publikování je pro mě nejlepší?](../ide/not-in-toc/web-publish-options.md).

## <a name="deploy-to-local-folder"></a>Nasazení do místní složky

Nasazení do místní složky se obvykle používá pro testování nebo zahájíte dvoufázové nasazení, ve kterém se použije jiný nástroj pro nasazení poslední.

- **ASP.NET**, **ASP.NET Core**, **Node.js**, **Python**, a. **Základní NET**: použijte nástroj pro publikování pro nasazení do místní složky. Možnosti dostupné závisí na typu vaší aplikace. V Průzkumníku řešení klikněte pravým tlačítkem na projekt a zvolte **publikovat**. (Pokud jste dříve nakonfigurovali žádné profily publikování, musíte pak kliknout na **vytvořit nový profil**.) V dalším kroku vyberte **složky**. Další informace najdete v tématu [nasadit do místní složky](quickstart-deploy-to-local-folder.md).

    ![Zvolte publikování](../deployment/media/quickstart-publish.png)

- **Visual C++ runtime**: můžete nasadit modulu runtime Visual C++ pomocí místního nasazení nebo statické propojení. Další informace najdete v tématu [nasazení nativních plochy aplikací (Visual C++)](/cpp/ide/deploying-native-desktop-applications-visual-cpp). 

## <a name="publish-to-azure"></a>Publikování v Azure

- **ASP.NET**, **ASP.NET Core**, **Python**, a **Node.js**: nástroj publikování můžete rychle nasadit aplikace do Azure App Service nebo virtuální Azure Počítač. V Průzkumníku řešení klikněte pravým tlačítkem na projekt a zvolte **publikovat**. (Pokud jste dříve nakonfigurovali žádné profily publikování, musíte pak kliknout na **vytvořit nový profil**.) V dialogovém okně Publikovat zvolit buď **služby App Service** nebo **virtuální počítače Azure**a pak postupujte podle kroků konfigurace.

    ![Vyberte aplikační služba Azure](../deployment/media/quickstart-publish-azure.png "vyberte aplikační služba Azure")

    V aplikaci Visual Studio 2017 verze 15.7, můžete nasadit aplikace ASP.NET Core **služby App Service pro Linux**.

    Informace o import profilu publikování ze služby Azure App Service pro Visual Studio najdete v tématu [importu nastavení publikování a nasazení do Azure](../deployment/tutorial-import-publish-settings-azure.md).

    Rychlý úvod najdete v části [publikovat do Azure](quickstart-deploy-to-azure.md). Další informace naleznete v [publikovat aplikaci ASP.NET Core do Azure](/aspnet/core/tutorials/publish-to-azure-webapp-using-vs). Nasazování pomocí Git, najdete v části [průběžné nasazování ASP.NET Core do Azure s Gitem](/aspnet/core/publishing/azure-continuous-deployment).

    > [!NOTE]
    > Pokud již účet Azure nemáte, můžete [zaregistrujte si zde](https://azure.microsoft.com/free/?ref=microsoft.com&utm_source=microsoft.com&utm_medium=doc&utm_campaign=visualstudio).

## <a name="publish-to-web-or-deploy-to-network-share"></a>Publikovat na Web nebo nasadit do sdílené síťové složky

- **ASP.NET**, **ASP.NET Core**, **Node.js**, a **Python**: nástroj publikování můžete nasadit k webu pomocí protokol FTP nebo Webdeploy. Další informace najdete v tématu [nasadit na web](quickstart-deploy-to-a-web-site.md).

    V Průzkumníku řešení klikněte pravým tlačítkem na projekt a zvolte **publikovat**. (Pokud jste dříve nakonfigurovali žádné profily publikování, musíte pak kliknout na **vytvořit nový profil**.) V nástroji pro publikování zvolte možnost chcete a postupujte podle kroků konfigurace.

    ![Zvolte služby IIS, FTP, atd.](../deployment/media/quickstart-publish-iis-ftp.png)

    Informace o import profilu publikování v sadě Visual Studio najdete v tématu [importu nastavení publikování a nasazení do služby IIS](../deployment/tutorial-import-publish-settings-iis.md).

    Můžete také nasadit aplikace ASP.NET a služby v několika jiné způsoby. Další informace najdete v tématu [nasazení webových aplikací a služeb ASP.NET](http://www.asp.net/aspnet/overview/deployment).

- **Visual C++ runtime**: můžete nasadit modulu runtime Visual C++ pomocí Centrální nasazení. Další informace najdete v tématu [nasazení nativních plochy aplikací (Visual C++)](/cpp/ide/deploying-native-desktop-applications-visual-cpp). 

- **Windows desktop** můžete publikovat aplikace systému Windows na webový server nebo do síťové sdílené složky pomocí ClickOnce – nasazení. Uživatelé pak mohou aplikaci nainstalovat jediným kliknutím. Další informace najdete v tématu [nasazení aplikace na ploše použitím technologie ClickOnce](how-to-publish-a-clickonce-application-using-the-publish-wizard.md) a [nasazení ClickOnce pomocí nativní aplikace](/cpp/ide/clickonce-deployment-for-visual-cpp-applications).

## <a name="publish-to-microsoft-store"></a>Publikovat do úložiště Microsoft

Ze sady Visual Studio můžete vytvořit balíčky aplikací pro nasazení Microsoft Store.

- **UWP**: můžete balíček aplikace a nasadit ho pomocí položky nabídky. Další informace najdete v tématu [balíček aplikace pro UPW pomocí sady Visual Studio](/windows/uwp/packaging/packaging-uwp-apps).

    ![Vytvoření balíčku aplikace](../deployment/media/feature-tour-create-app-package.jpg)

- **Windows desktop**: můžete nasadit na Microsoft Store pomocí most plochy od verze Visual Studio 2017 verzi 15.4. Chcete-li to provést, začněte vytvořením balení projekt aplikace Windows. Další informace najdete v tématu [balíčku aplikace na ploše pro Microsoft Store (Desktop mostu)](/windows/uwp/porting/desktop-to-uwp-packaging-dot-net).

    ![Plochy most](../deployment/media/feature-tour-desktop-bridge.png)

## <a name="deploy-to-a-device-uwp"></a>Nasazení do zařízení (UWP)

Pokud nasazujete aplikaci UWP k testování na zařízení, najdete v části [aplikace UWP spustit na vzdáleném počítači v sadě Visual Studio](../debugger/run-windows-store-apps-on-a-remote-machine.md).

## <a name="create-an-installer-package-windows-client"></a>Vytvoření balíčku Instalační služby (klienta Windows)

Pokud požadujete víc o komplexní instalaci aplikace pracovní plochy než [ClickOnce](how-to-publish-a-clickonce-application-using-the-publish-wizard.md) můžete zadat, můžete vytvořit balíček instalačního programu, projekt instalace nebo vlastního zaváděcího nástroje.

- Instalační program na základě MSI WiX lze vytvořit pomocí [WiX Toolset 2017 rozšíření sady Visual Studio](https://marketplace.visualstudio.com/items?itemName=RobMensching.WixToolsetVisualStudio2017Extension).

- [InstallShield](https://www.flexerasoftware.com/producer/products/software-installation/installshield-software-installer/tab/requirements) Flexera softwaru může být použit s Visual Studio 2017 (Community Edition není podporován). Všimněte si, že InstallShield Limited Edition je už součástí sady Visual Studio a není podporován v Visual Studio 2017; Obraťte se na [Flexera softwaru](http://learn.flexerasoftware.com/content/IS-EVAL-InstallShield-Limited-Edition-Visual-Studio) o budoucí dostupnosti.

- Pokud chcete vytvořit projekt instalace (vdproj), nainstalujte [instalační program projektů sady Visual Studio 2017 rozšíření](https://marketplace.visualstudio.com/items?itemName=VisualStudioProductTeam.MicrosoftVisualStudio2017InstallerProjects#overview).

- Konfigurace obecný instalační program, který se označuje jako zaváděcí nástroj, můžete nainstalovat požadované součásti pro aplikací klasické pracovní plochy. Další informace najdete v tématu [nezbytné součásti nasazení aplikace](../deployment/application-deployment-prerequisites.md).

## <a name="deploy-to-test-lab"></a>Nasazení do testovací laboratoře

Můžete povolit složitější vývoj a testování nasazení vaší aplikace do virtuálního prostředí. Další informace najdete v tématu [testů v testovacím prostředí](../test/lab-management/using-a-lab-environment-for-your-application-lifecycle.md).

## <a name="devops-deployment"></a>DevOps nasazení

V prostředí team můžete povolit průběžné nasazování aplikace Visual Studio Team Services (VSTS). Další informace najdete v tématu [sestavení a verze](/vsts/build-release/index) a [nasadit do Azure](/vsts/deploy-azure/index).

## <a name="deployment-for-other-app-types"></a>Nasazení pro jiné typy aplikací

| Typ aplikace | Scénář nasazení | Odkaz |
| --- | --- | --- |
| **Aplikace Office** | Můžete publikovat doplňku pro Office v sadě Visual Studio. | [Nasazení a publikování tohoto doplňku Office](https://dev.office.com/docs/add-ins/publish/publish) |
| **Služby WCF nebo OData**  | Ostatní aplikace můžou využívat WCF RIA services, které nasazujete na webový server. | [Vývoj a nasazení služby WCF Data Services](/dotnet/framework/data/wcf/developing-and-deploying-wcf-data-services) |
| **LightSwitch** | Již není podporována v Visual Studio 2017 LightSwitch, ale mohou být nasazeny stále ze sady Visual Studio 2015 a starší. | [Nasazování aplikací LightSwitch](http://msdn.microsoft.com/Library/4818d933-295c-4ecc-9148-7ad9ca28dcdb) | 

## <a name="next-steps"></a>Další kroky

V tomto kurzu trvalo rychle zobrazit možnosti nasazení pro různé aplikace. Pokud nasazujete webovou aplikaci, jako je ASP.NET, přečtěte si podrobnější informace o některých možností nasazení k dispozici v sadě Visual Studio.

> [!div class="nextstepaction"]
> [Jaké možnosti publikování je pro mě nejlepší?](../ide/not-in-toc/web-publish-options.md)

