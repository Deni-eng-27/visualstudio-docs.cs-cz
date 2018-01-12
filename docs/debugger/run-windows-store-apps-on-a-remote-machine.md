---
title: "Spuštění aplikace UPW a Windows 8.1 ve vzdáleném počítači | Microsoft Docs"
ms.custom: 
ms.date: 01/05/2018
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: 0f6814d6-cd0d-49f3-b501-dea8c094b8ef
caps.latest.revision: "43"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: uwp
ms.openlocfilehash: 3e27aae0b9a8e57575015d1d8d5baee3803959a9
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="run-uwp-and-windows-81-apps-on-a-remote-machine"></a>Spuštění aplikace UPW a Windows 8.1 ve vzdáleném počítači  
  
Ke spuštění aplikace UPW nebo Windows 8.1 ve vzdáleném počítači, je nutné připojit se pomocí nástroje Remote Tools pro sadu Visual Studio. Nástroje remote tools umožňují spouštět, ladit, profil a testování aplikace pro UPW, která běží na jedno zařízení z druhého počítače, který běží v sadě Visual Studio. Spuštění na vzdáleném zařízení může být zvláště efektivní, když počítač Visual Studio nepodporuje funkce, které jsou specifické pro aplikace UWP, například dotykového ovládání, geografického umístění a fyzické orientace. Toto téma popisuje postupy pro konfiguraci a spouští vzdálenou relaci.

V některých scénářích nástrojů pro vzdálenou automaticky nainstaluje, když nasadíte na vzdáleném zařízení.

- Pro počítače s Windows 10 systémem Creators aktualizace a novější verze budou automaticky nainstalovány nástroje pro vzdálenou.
- Pro zařízení s Windows 10 Xbox, IOT a HoloLens budou automaticky nainstalovány nástroje pro vzdálenou.
- Pro Windows Phone, musíte být fyzicky připojení k telefonu, je třeba nainstalovat [licence pro vývojáře](https://msdn.microsoft.com/en-us/library/windows/apps/xaml/hh974578.aspx) (Windows Phone 8 a 8.1), nebo povolte [režim vývojáře](/windows/uwp/get-started/enable-your-device-for-development) (Windows Mobile 10), a vy musíte Vyberte **zařízení** jako cíl ladění. Nástroje pro vzdálenou nejsou požadovaná nebo podporované.

Pro počítače s Windows 8.1 a počítače s Windows 10 pre-Creator aktualizace verzí systému Windows nainstalujte nástroje pro vzdálenou ve vzdáleném počítači ručně předtím, než můžete ladit. Postupujte podle pokynů v tomto tématu. 
  
##  <a name="BKMK_Prerequisites"></a>Požadavky  
 Ladění na vzdáleném zařízení:  
  
-   Vzdálené zařízení a počítače Visual Studio musí být připojené přes síť, nebo připojené přímo pomocí kabelu USB nebo sítě Ethernet. Ladění po Internetu není podporováno.  

- Vzdálené zařízení musí být povolen pro vývoj.

    - Pro zařízení s Windows 8 a Windows 8.1 [licence pro vývojáře](https://msdn.microsoft.com/en-us/library/windows/apps/xaml/hh974578.aspx) musí být nainstalován na vzdáleném zařízení.
    - Pro zařízení s Windows 10, musíte povolit [režim vývojáře](/windows/uwp/get-started/enable-your-device-for-development). 
  
-   Pro počítače s Windows 10 s verzí systému Windows 10 starší než Windows 10 Creator aktualizace, je nutné [instalaci a spuštění vzdáleného ladění součásti](#BKMK_download).
  
##  <a name="BKMK_Security"></a>Zabezpečení  
Ve výchozím nastavení **Universal (nešifrovaného protokolu)** se používá ve Windows 10. Tuto protokolu lze používat pouze v důvěryhodných sítích. Ladění připojení je zranitelný vůči uživateli se zlými úmysly kteří může zachytávat a měnit data, které jsou předávány mezi vývoj a vzdáleného počítače.
  
> [!WARNING]
>  Neexistuje žádné zabezpečení sítě, když nastavíte režim ověřování na **Universal (nešifrovaného protokolu)** nebo **žádné**. Zvolte těchto režimech pouze v případě, že jste si jisti, že síť není hrozí od provozu škodlivý nebo k tomuto účelu.  
  
##  <a name="BKMK_DirectConnect"></a>Jak se připojit přímo pomocí kabelu USB 

Ve Windows 10, můžete nasadit do zařízení připojená k portu USB výběrem **zařízení** místo **vzdáleného počítače** jako cíl nasazení (můžete to provést **standardní** panelu nástrojů nebo na stránce vlastností ladění). Pro Windows 8.1 musí být nainstalované vzdálené nástroje na zařízení, než se můžete připojit přímo.

##  <a name="BKMK_ConnectVS"></a>Konfigurace projektu Visual Studia pro vzdálené ladění  
 Zadejte vzdálené zařízení pro připojení k ve vlastnostech projektu. Postup se liší v závislosti na programovací jazyk. Můžete zadat síťový název vzdáleného zařízení nebo můžete vybrat z **vzdáleného připojení** dialogové okno.  
  
 ![Dialogové okno Vyberte připojení vzdáleného ladicího programu](../debugger/media/vsrun_selectremotedebuggerdlg.png "VSRUN_SelectRemoteDebuggerDlg")  
  
 Dialogové okno zobrazí jenom ta zařízení, které jsou v místní podsíti počítače Visual Studio a, na kterých běží vzdáleného ladicího programu.  
  
> [!TIP]
>  Pokud máte potíže s připojením ke vzdálené zařízení, zkuste zadat IP adresu zařízení. Pokud chcete určit IP adresu zařízení, otevřete okno příkazového řádku a zadejte **ipconfig**. IP adresa je uveden jako **IPv4 adresu**.  
  
###  <a name="BKMK_Choosing_the_remote_device_for_C__and_Visual_Basic_projects"></a>Vyberte vzdálené zařízení pro projekty C# a Visual Basic  
  
1.  Vyberte název projektu v Průzkumníku řešení a potom zvolte **vlastnosti** z místní nabídky.  
  
2.  Vyberte **ladění**.  
  
3.  Zvolte **vzdáleného počítače** z **cílové zařízení** seznamu.  
  
4.  Zadejte název vzdáleného zařízení v síti **vzdáleného počítače** pole nebo zvolte **najít** vybrat ze zařízení **vyberte připojení vzdáleného ladicího programu** dialogové okno. 

    ![Spravovat vlastnosti projektu pro vzdálené ladění](../debugger/media/vsrun_managed_projprop_remote.png "VSRUN_Managed_ProjProp_Remote")  
  
###  <a name="BKMK_Choosing_the_remote_device_for_JavaScript_and_C___projects"></a>Vyberte vzdálené zařízení pro projekty JavaScript a C++  
  
1.  Vyberte název projektu v Průzkumníku řešení a potom zvolte **vlastnosti** z místní nabídky.  
  
2.  Rozbalte **vlastnosti konfigurace** uzel a potom vyberte **ladění**.  
  
3.  Zvolte **vzdáleného ladicího programu** z **ladicí program ke spuštění** seznamu.  
  
4.  Zadejte název vzdáleného zařízení v síti **název počítače** pole nebo zvolte na šipku dolů do pole vybrat ze zařízení **vyberte připojení vzdáleného ladicího programu** dialogové okno.  

    ![C & č. 43; & č. 43; vlastnosti pro vzdálené ladění projektu](../debugger/media/vsrun_cpp_projprop_remote.png "VSRUN_CPP_ProjProp_Remote")
  
## <a name="BKMK_download"></a>Stáhněte a nainstalujte nástroje pro vzdálenou (předběžné Creators aktualizace)

Pokud používáte Windows 8.1 nebo pre-Creator aktualizace verze systému Windows 10, postupujte podle těchto pokynů. Jinak můžete tuto část přeskočit.

[!INCLUDE [remote-debugger-download](../debugger/includes/remote-debugger-download.md)]
  
### <a name="BKMK_setup"></a>Nastavení vzdáleného ladicího programu

[!INCLUDE [remote-debugger-configuration](../debugger/includes/remote-debugger-configuration.md)]  
  
##  <a name="BKMK_RunRemoteDebug"></a>Spustit relaci vzdáleného ladění  
 Spuštění, zastavení a přechod na relaci vzdáleného ladění stejným způsobem jako místní relace. Na verze pre-Creator aktualizace systému Windows 10 zkontrolujte, zda že je spuštěna Remote Debugging Monitor na vzdáleném zařízení.  
  
 Zvolte **spustit ladění** na **ladění** nabídky (klávesové: F5). Projekt je překompilovat, pak nasazené a spustit na vzdáleném zařízení. Ladicí program pozastaví spuštění na zarážkách a můžete krok do, přes a z vašeho kódu. Zvolte **Zastavte ladění** ukončete svou relaci ladění a zavřete vzdálené aplikace. Další informace najdete v tématu [ladění aplikací v sadě Visual Studio](../debugger/debug-store-apps-in-visual-studio.md).  
  
## <a name="see-also"></a>Viz také  
 [Testování aplikací pro UPW pomocí sady Visual Studio](../test/testing-store-apps-with-visual-studio.md)   
 [Ladění aplikací v sadě Visual Studio](../debugger/debug-store-apps-in-visual-studio.md)