---
title: Spustit jako správce
ms.date: 06/05/2018
ms.topic: conceptual
helpviewer_keywords:
- Visual Studio, user permissions
- user permissions
- administrative privileges
- permissions
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 229b1606a8a7de18da7354852e3e5adb9123f5b5
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62821640"
---
# <a name="user-permissions-and-visual-studio"></a>Uživatelská oprávnění a sada Visual Studio

Z důvodů zabezpečení byste měli spustit Visual Studio v režimu normálního uživatele, kdykoli je to možné.

> [!WARNING]
> Je třeba zajistit, aby nebylo kompilováno, spouštěno nebo laděno jakékoli řešení systému Visual Studio, které nebylo získáno od důvěryhodné osoby nebo z důvěryhodného zdroje.

V režimu normálního uživatele lze provádět téměř cokoli v integrovaném vývojovém prostředí sady Visual Studio. Budete potřebovat oprávnění správce k následujícím postupem:

|Oblast|Úloha|Další informace|
|----------|----------| - |
|Instalace|Instalace sady Visual Studio.|[Instalace sady Visual Studio](../install/install-visual-studio.md)|
||Instalace, aktualizace nebo odebrání místního obsahu nápovědy.|[Nainstalovat a spravovat místní obsah nápovědy](../help-viewer/install-manage-local-content.md)|
|Sada nástrojů|Přidat klasické ovládací prvky modelu COM pro **nástrojů**.|[Panel nástrojů](../ide/reference/toolbox.md)|
|Sestavování|Události po sestavení, které registrují komponentu použijte.|[Vlastní kroky sestavení porozumět a vybudovat události](/cpp/ide/understanding-custom-build-steps-and-build-events)|
||Zahrnout krok registrace při vytváření projektů v jazyce C++.||
|Ladění|Ladění aplikací spouštěných se zvýšenými oprávněními.|[Nastavení a příprava ladicího programu](../debugger/debugger-settings-and-preparation.md)|
||Ladění aplikací, které běží pod jiným uživatelským účtem, jako jsou weby ASP.NET.|[Ladění aplikací ASP.NET a AJAX](../debugger/how-to-enable-debugging-for-aspnet-applications.md)|
||Ladění v zóně pro aplikace prohlížeče XAML (XBAP).|[Hostitel WPF (PresentationHost.exe)](/dotnet/framework/wpf/app-development/wpf-host-presentationhost-exe)|
||Použití emulátoru k ladění projektů cloudových služeb pro Microsoft Azure.|[Ladění cloudové služby v sadě Visual Studio](/azure/vs-azure-tools-debug-cloud-services-virtual-machines)|
||Konfigurace brány firewall pro vzdálené ladění.|[Vzdálené ladění](../debugger/remote-debugging.md)|
|Nástroje pro měření výkonu|Profilace aplikace|[Průvodce začátečníka profilací výkonu](../profiling/beginners-guide-to-performance-profiling.md)|
|Nasazení|Nasazení webové aplikace do Internetové informační služby (IIS) na místním počítači.|[Nasazení webové aplikace ASP.NET pomocí sady Visual Studio](/aspnet/web-forms/overview/older-versions-getting-started/deployment-to-a-hosting-provider/)|

## <a name="run-visual-studio-as-an-administrator"></a>Spuštění sady Visual Studio jako správce

Pokud je potřeba spustit aplikaci Visual Studio jako správce, otevřete integrovaného vývojového prostředí pomocí těchto kroků:

> [!NOTE]
> Tyto pokyny jsou určené pro Windows 10. Když se podobají u jiných verzí Windows.

::: moniker range="vs-2017"

1. Otevřít **Start** nabídky a přejděte do sady Visual Studio 2017.

1. Z nabídky klikněte pravým tlačítkem nebo kontext **Visual Studio 2017**vyberte **Další** > **spustit jako správce**.

   Při spuštění sady Visual Studio **(správce)** se zobrazí za názvem produktu v záhlaví programu.

::: moniker-end

::: moniker range=">=vs-2019"

1. Otevřít **Start** nabídky a přejděte k Visual Studio 2019.

1. Z nabídky klikněte pravým tlačítkem nebo kontext **Visual Studio 2019**vyberte **Další** > **spustit jako správce**.

   Při spuštění sady Visual Studio **(správce)** se zobrazí za názvem produktu v záhlaví programu.

::: moniker-end

Můžete také upravit zástupce sady tak aby se vždy spustila s oprávněními správce.

## <a name="see-also"></a>Viz také:

- [Přenos, migrace a upgrade projektů sady Visual Studio](../porting/port-migrate-and-upgrade-visual-studio-projects.md)
- [Instalace sady Visual Studio](../install/install-visual-studio.md)