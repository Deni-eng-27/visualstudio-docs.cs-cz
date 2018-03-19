---
title: "Konfigurace služby ASP.NET Profiler pro zátěžové testy v sadě Visual Studio | Microsoft Docs"
ms.date: 10/13/2016
ms.topic: article
helpviewer_keywords:
- test settings, ASP.NET
ms.assetid: 6832fe39-04d5-4d94-8a18-3e2730bad423
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-test
ms.openlocfilehash: b647b032ced1d0d8faf6d5fd5fd293c42cfbfad9
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/19/2018
---
# <a name="how-to-configure-aspnet-profiler-for-load-tests-using-test-settings-in-visual-studio"></a>Postupy: Konfigurace služby ASP.NET Profiler pro zátěžové testy s využitím testovacích nastavení v sadě Visual Studio

Adaptér diagnostických dat profileru ASP.NET můžete použít ke shromažďování informací profileru ASP.NET. Tento adaptér diagnostických dat shromažďuje údaje o výkonu pro aplikace ASP.NET.

> [!NOTE]
> Tento adaptér diagnostických dat nelze použít pro testy, které jsou spouštěny pomocí nástroje Microsoft Test Manager. Můžete použít adaptéru diagnostických ASP.NET Profiler se zátěžovými testy pomocí pouze weby který vyžaduje Visual Studio Enterprise.

Adaptér diagnostických dat profileru ASP.NET umožňuje shromažďovat data technologie ASP.NET profileru z vrstvy aplikace při spuštění zátěžového testu. Profiler by neměl být spouštěn pro dlouho trvající testy, například pro zátěžové testy, které trvají déle než jednu hodinu. Důvodem je, že soubor profileru může dosáhnout velikosti až stovek megabajtů. Místo toho spustíte kratší zátěžových testů ASP.NET profiler, který pořád dá výhodou hloubkové diagnóza problémy s výkonem.

> [!NOTE]
> Adaptér diagnostických dat profileru ASP.NET profily proces Internetové informační služby (IIS). Proto nebude fungovat oproti vývojovému webovému serveru. Pro profilování webové stránky v zátěžovém testu je nutné nainstalovat testovací agent na počítači, na kterém služby IIS běží. Testovací agent nebude generovat zátěž, ale bude to agent pouze pro sběr. Další informace najdete v tématu [instalace a konfigurace testovacích agentů](../test/lab-management/install-configure-test-agents.md).

Další informace najdete v tématu [postupy: vytvoření nastavení testu pro zátěžový Test distribuované](../test/how-to-create-a-test-setting-for-a-distributed-load-test.md).

Následující postup popisuje, jak nakonfigurovat adaptér diagnostických dat pro ASP.NET profiler.

## <a name="to-configure-the-aspnet-profiler-for-your-test-settings"></a>Konfigurace profileru technologie ASP.NET pro nastavení testu

Před provedením kroků v tomto postupu, je nutné otevřít nastavení testů ze sady Visual Studio a vybrat **datové a diagnostické** stránky.

### <a name="to-configure-the-aspnet-profiler-for-your-test-settings"></a>Konfigurace profileru technologie ASP.NET pro nastavení testu

1.  Vyberte role, kterou chcete použít ke shromažďování dat profileru ASP.NET.

    > [!WARNING]
    > Tato role musí být webový server.

2.  Vyberte **ASP.NET Profiler** Povolit shromažďování dat profilace ASP.NET, a potom zvolte **konfigurace**.

     Zobrazí se dialogové okno Konfigurace shromažďování dat profilace ASP.NET.

3.  V **interval vzorkování profileru**, zadejte hodnotu, která určuje, kolik-zastavit procesoru taktovací cykly čekat mezi pořizováním ASP.NET profilace ukázky.

4.  Chcete-li profilace interakce vrstvy, vyberte **povolit profilace interakce vrstvy**.

     Profilování interakce vrstev počítá počet požadavků, které byly na webový server odeslány pro každý artefakt (například MyPage.aspx nebo CompanyLogo.gif), a dobu obsloužení jednotlivých požadavků. Profilování interakce vrstev dále shromažďuje informace o tom, která připojení ADO.NET byla použita jako součást požadavku na stránku a kolik dotazů a volání uložené procedury bylo provedeno jako součást řešení této žádosti.

     Jsou shromažďovány dvě různé sady informací o časování:

    -   Informace o časování (minimum, maximum, průměr a součet) pro obsluhu každého webového požadavku.

    -   Informace o časování (minimum, maximum, průměr a součet) spuštění každého dotazu.

S ASP.NET profiler adaptér diagnostických dat nakonfigurované v nastavení vašeho testu můžete nyní shromáždit ASP.NET profilace data na vaší webové aplikace ASP.NET.

## <a name="see-also"></a>Viz také

- [Shromažďování diagnostických informací s použitím nastavení testu](../test/collect-diagnostic-information-using-test-settings.md)
- [Postupy: vytvoření nastavení testu pro distribuovaný zátěžový Test](../test/how-to-create-a-test-setting-for-a-distributed-load-test.md)
- [Testovací kontrolery a testovací agenti](configure-test-agents-and-controllers-for-load-tests.md)