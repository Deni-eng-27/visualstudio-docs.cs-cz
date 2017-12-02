---
title: "Vzdálené ladění ASP.NET Core v počítači vzdálené služby IIS | Microsoft Docs"
ms.custom: remotedebugging
ms.date: 08/14/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 573a3fc5-6901-41f1-bc87-557aa45d8858
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b73dc5b153813811a0d2b839e69200a7e5f5a1e9
ms.sourcegitcommit: 5f5587a1bcf4aae995c80d54a67b4b461f8695f3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/29/2017
---
# <a name="remote-debug-aspnet-core-on-a-remote-iis-computer-in-visual-studio-2017"></a>Vzdálené ladění ASP.NET Core na počítači vzdálené služby IIS v Visual Studio 2017
K ladění aplikace ASP.NET, která byla nasazena do služby IIS, instalaci a spuštění nástrojů pro vzdálenou na počítači, kde jste nasadili aplikace a pak připojte k běžící aplikaci ze sady Visual Studio.

![Součásti vzdáleného ladicího programu](../debugger/media/remote-debugger-aspnet.png "Remote_debugger_components")

Tato příručka vysvětluje, jak nastavit a konfigurovat Visual Studio 2017 ASP.NET Core, nasazení pro službu IIS a připojení vzdáleného ladicího programu ze sady Visual Studio. Vzdálené ladění ASP.NET 4.5.2, najdete v tématu [vzdáleného ladění ASP.NET na počítači se službou IIS](../debugger/remote-debugging-aspnet-on-a-remote-iis-7-5-computer.md). Také můžete nasazovat a ladění ve službě IIS pomocí Azure. Další informace najdete v tématu [vzdáleného ladění na Azure](../debugger/remote-debugging-azure.md).

Tyto postupy jsme otestovali na tyto konfigurace serveru:
* Windows Server 2012 R2 a služby IIS 8
* Windows Server 2016 a IIS 10

## <a name="requirements"></a>Požadavky

Mezi dvěma počítači připojené prostřednictvím proxy serveru se nepodporuje ladění. Ladění nad vysokou latencí nebo připojení s malou šířkou pásma, například telefonického Internetu, nebo přes Internet napříč zemích se nedoporučuje a může selhat nebo být příliš pomalé. Úplný seznam požadavků, najdete v části [požadavky](../debugger/remote-debugging.md#requirements_msvsmon).

## <a name="create-the-aspnet-core-application-on-the-visual-studio-2017-computer"></a>Vytvoření aplikace ASP.NET Core v počítači Visual Studio 2017 

1. Vytvoření nové aplikace ASP.NET Core. (**Soubor > Nový > projekt**, pak vyberte **Visual C# > Web > webové aplikace ASP.NET Core (.NET Core)**).

    V **ASP.NET Core** část šablony, vyberte **webové aplikace**.

2. Ujistěte se, že **povolení podpory Docker** je **není** vybrané a že **ověřování** je nastaven na **bez ověřování**.

3. Název projektu **MyASPApp** a klikněte na tlačítko **OK** k vytvoření nové řešení.

4. Otevřete soubor About.cshtml.cs a nastavte zarážky `OnGet` – metoda (v starší šablony, otevřete místo nich HomeController.cs a nastavit bod přerušení `About()` metoda).

## <a name="bkmk_configureIIS"></a>Instalace a konfigurace služby IIS v systému Windows Server

[!INCLUDE [remote-debugger-install-iis-role](../debugger/includes/remote-debugger-install-iis-role.md)]

## <a name="update-browser-security-settings-on-windows-server"></a>Aktualizovat nastavení zabezpečení prohlížeče v systému Windows Server

V závislosti na nastavení zabezpečení se může ušetřit čas přidat následující důvěryhodných serverů na prohlížeč, abyste si můžete snadno stáhnout software popsané v tomto kurzu. Může být potřeba přístup k těchto lokalit:

- Microsoft.com
- go.microsoft.com
- download.microsoft.com
- VisualStudio.com

Pokud používáte Internet Explorer, můžete přidat důvěryhodných serverů přechodem na **Možnosti Internetu > zabezpečení > důvěryhodných serverů > lokality**. Tyto kroky jsou u jiných prohlížečů. (Pokud budete muset stáhnout starší verze vzdáleného ladicího programu z my.visualstudio.com, některé další důvěryhodných serverů jsou nutné k přihlášení.)

Při stahování softwaru, může dojít k žádosti o udělení oprávnění ke spouštění různých skripty webu a prostředky. Ve většině případů není tyto další prostředky nutné k instalaci softwaru.

## <a name="install-aspnet-core-on-windows-server"></a>Instalace jádra ASP.NET v systému Windows Server

1. Nainstalujte [hostování v rozhraní .NET Core systému Windows Server](https://aka.ms/dotnetcore-2-windowshosting) sady v hostitelském systému. Sada nainstaluje .NET Core Runtime, knihovny .NET Core a modulu jádra ASP.NET. Další podrobné pokyny najdete v tématu [publikování do služby IIS](/aspnet/core/publishing/iis?tabs=aspnetcore2x#iis-configuration).

    > [!NOTE]
    > Pokud systém nemá připojení k Internetu, získejte a nainstalujte  *[Microsoft Visual C++ 2015 Redistributable](https://www.microsoft.com/download/details.aspx?id=53840)*  před instalací sady hostování v rozhraní .NET Core systému Windows Server.

3. Restartování systému (nebo spuštění **net stop byl /y** následuje **net start w3svc** z příkazového řádku a pokračovat tam ke změně systému cesta).

## <a name="BKMK_install_webdeploy"></a>(Volitelné) Nasazení webu instalace 3.6 v systému Windows Server

[!INCLUDE [remote-debugger-install-web-deploy](../debugger/includes/remote-debugger-install-web-deploy.md)]

## <a name="BKMK_deploy_asp_net"></a>Konfigurace webu ASP.NET na počítač s Windows serverem

1. Otevřete Průzkumníka Windows a vytvořte novou složku, **C:\Publish**, kde později nasadíte projekt ASP.NET.

2. Otevřete **Internetová informační služba (IIS) Manager**. (V levém podokně Správce serveru, vyberte **IIS**. Pravým tlačítkem na server a vyberte **Správce Internetové informační služby (IIS)**.)

3. V části **připojení** v levém podokně přejděte do **lokality**.

4. Vyberte **Default Web Site**, zvolte **základní nastavení**a nastavte **fyzická cesta** k **C:\Publish**.

4. Klikněte pravým tlačítkem myši **Default Web Site** uzel a vyberte možnost **přidat aplikaci**.

5. Nastavte **Alias** do **MyASPApp**, přijměte výchozí nastavení fondu aplikací (**DefaultAppPool**) a nastavte **fyzická cesta** k  **C:\Publish**.

6. V části **připojení**, vyberte **fondy aplikací**. Otevřete **DefaultAppPool** a nastavte hodnotu pole fondu aplikací na **bez spravovaného kódu**.

7. Klikněte pravým tlačítkem na novou lokalitu ve Správci služby IIS, zvolte **upravit oprávnění**a ujistěte se, že IUSR, IIS_IUSRS nebo uživatel nakonfigurovaný pro přístup do webové aplikace je oprávněný uživatel s oprávněními Číst a spouštět.

    Pokud nevidíte jeden z těchto uživatelů s přístupem, projít kroky k přidání IUSR jako uživatel s právy ke čtení a spouštění.

## <a name="bkmk_webdeploy"></a>(Volitelné) Publikujte a nasaďte aplikace pomocí nasazení webu ze sady Visual Studio

[!INCLUDE [remote-debugger-deploy-app-web-deploy](../debugger/includes/remote-debugger-deploy-app-web-deploy.md)]

## <a name="optional-publish-and-deploy-the-app-by-publishing-to-a-local-folder-from-visual-studio"></a>(Volitelné) Publikujte a nasaďte aplikaci pomocí publikování do místní složky ze sady Visual Studio

Můžete také publikovat a nasazení aplikace pomocí systému souborů nebo jiných nástrojů.

[!INCLUDE [remote-debugger-deploy-app-local](../debugger/includes/remote-debugger-deploy-app-local.md)]

## <a name="BKMK_msvsmon"></a>Stáhněte a nainstalujte nástroje pro vzdálenou v systému Windows Server

[!INCLUDE [remote-debugger-download](../debugger/includes/remote-debugger-download.md)]

> [!TIP]
> V některých případech může být nejúčinnější ke spuštění vzdáleného ladicího programu ze sdílené složky. Další informace najdete v tématu [spuštění vzdáleného ladicího programu ze sdílené složky](../debugger/remote-debugging.md#fileshare_msvsmon).
  
## <a name="BKMK_setup"></a>Nastavení vzdáleného ladicího programu v systému Windows Server

[!INCLUDE [remote-debugger-configuration](../debugger/includes/remote-debugger-configuration.md)]

> [!NOTE]
> Pokud potřebujete přidat oprávnění pro všechny další uživatele, změna režimu ověřování, nebo číslo portu pro vzdáleného ladicího programu, najdete v části [konfigurovat vzdálený ladicí program](../debugger/remote-debugging.md#configure_msvsmon).

Informace o spuštění jako služba vzdáleného ladicího programu najdete v tématu [spuštěn jako služba vzdáleného ladicího programu](../debugger/remote-debugging.md#bkmk_configureService).

## <a name="BKMK_attach"></a>Připojení k aplikaci ASP.NET z počítače, Visual Studio

1. Otevřete v sadě Visual Studio počítači, **MyASPApp** řešení.
2. V sadě Visual Studio, klikněte na tlačítko **ladění > připojit k procesu** (Ctrl + Alt + P).

    > [!TIP]
    > V aplikaci Visual Studio 2017, může do stejného procesu dříve připojen k pomocí připojte **ladění > připojte k procesu...** (Shift + Alt + P). 

3. Nastavte hodnotu pole kvalifikátor na  **\<název vzdáleného počítače >: 4022**.
4. Klikněte na tlačítko **aktualizovat**.
    Měli byste vidět některé procesy, které se zobrazí v **dostupné procesy** okno.

    Pokud nevidíte žádné procesy, zkuste pomocí IP adresy místo název vzdáleného počítače (port je vyžadováno). Můžete použít `ipconfig` v příkazovém řádku, potřebujete adresu IPv4.

    Pokud chcete použít **najít** tlačítko, budete muset [otevřete UDP port 3702](#bkmk_openports) na serveru.

5. Zkontrolujte **Zobrazit procesy od všech uživatelů**.
6. Zadejte první písmeno názvu procesu a rychle tak najít **dotnet.exe** (pro ASP.NET Core).

    ![RemoteDBG_AttachToProcess](../debugger/media/remotedbg_attachtoprocess_aspnetcore.png "RemoteDBG_AttachToProcess")

7. Klikněte na tlačítko **připojit**.

8. Otevřete web vzdáleného počítače. V prohlížeči přejděte na **http://\<název vzdáleného počítače >**.
    
    Měli byste vidět webová stránka ASP.NET.

9. V běžící aplikaci ASP.NET, klikněte na odkaz **o** stránky.

    Zarážce by měl být dosáhl v sadě Visual Studio.

## <a name="bkmk_openports"></a>Řešení potíží: Otevřete požadované porty v systému Windows Server

Ve většině nastavení jsou otevřené požadované porty při instalaci ASP.NET a vzdáleného ladicího programu. Potřebujete však ověřte, že jsou otevřené porty.

> [!NOTE]
> Ve virtuálním počítači Azure, musíte otevřít porty prostřednictvím [skupinu zabezpečení sítě](/azure/virtual-machines/virtual-machines-windows-hero-role#open-port-80). 

Požadované porty:

- 80 - požadované pro službu IIS
- 4022 - požadované pro vzdálené ladění z Visual Studio 2017 (viz [přiřazení portu vzdáleného ladicího programu](../debugger/remote-debugger-port-assignments.md) podrobné informace.
- 8172 – (volitelné) vyžaduje se pro nasazení webu pro nasazení aplikace z Visual Studia.
- UDP 3702 - port (volitelné) zjišťování umožňuje **najít** tlačítko při připojování k vzdáleného ladicího programu v sadě Visual Studio.

1. Chcete-li otevřít port v systému Windows Server, otevřete **spustit** nabídky, vyhledejte **brány Windows Firewall s pokročilým zabezpečením**.

2. Zvolte **příchozí pravidla > nové pravidlo > Port**a potom klikněte na **Další**. (UDP 3702, zvolte **odchozí pravidla** místo.)

3. V části **určité místní porty**, zadejte číslo portu, klikněte na **Další**.

4. Klikněte na tlačítko **povolit připojení**, klikněte na tlačítko **Další**.

5. Vyberte jeden nebo více typů sítě povolit pro port a klikněte na tlačítko **Další**.

    Typ, který jste vybrali musí zahrnovat sítě, ke které je připojený vzdáleného počítače.
6. Přidejte název (například **IIS**, **Web Deploy**, nebo **msvsmon**) pro příchozí pravidlo a klikněte na tlačítko **Dokončit**.

    Měli byste vidět nové pravidlo v seznamu pravidel příchozí nebo odchozí pravidla.

    Pokud chcete další informace o konfiguraci brány Windows Firewall, najdete v části [konfigurace brány Windows Firewall pro vzdálené ladění](../debugger/configure-the-windows-firewall-for-remote-debugging.md).

3. Vytvořte další pravidla pro požadované porty.
