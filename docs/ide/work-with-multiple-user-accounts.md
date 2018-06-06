---
title: Práce s několika uživatelskými účty
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-acquisition
ms.topic: conceptual
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: edbe53458eafa833287cf48fec4870987a8ba81b
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/04/2018
ms.locfileid: "34749168"
---
# <a name="work-with-multiple-user-accounts"></a>Práce s několika uživatelskými účty

Pokud máte více účty Microsoft nebo pracovní nebo školní účty, můžete ho přidat do sady Visual Studio, tak, aby vám přístup k prostředkům z libovolného účtu bez nutnosti Přihlaste se k němu samostatně. Služby Azure, Application Insights, Team Foundation Server a Office 365 v současné době podporují zjednodušenou přihlašování uživatelů. Další služby se může stát odehrává k dispozici.

Po přidání více účtů na jednom počítači, bude tuto sadu účtů přemístit s vámi, při přihlášení k sadě Visual Studio na jiném počítači. Je důležité si uvědomit, že i když dojde k přemístění názvy účtů, není provádět přihlašovací údaje. Proto zobrazí se výzva k zadání přihlašovacích údajů pro tyto další účty poprvé pokusí použít jejich prostředky na nový počítač.

Tento návod ukazuje, jak přidat více účtů pro Visual Studio, a jak zjistit, že prostředky přístupné z těchto účtů se projeví v umístí, jako **přidat připojení službě** dialogu **Průzkumníka serveru** , a **Team Explorer**.

## <a name="sign-in-to-visual-studio"></a>Přihlášení k sadě Visual Studio

- Přihlaste se k sadě Visual Studio s účtem Microsoft nebo účtu organizace. Měli byste vidět svoje uživatelské jméno se zobrazí v horním rohu okna, podobně jako tento:

     ![Currentlly přihlášeného uživatele](../ide/media/vs2015_username.png)

### <a name="access-your-azure-account-in-server-explorer"></a>Přístup k účtu Azure v Průzkumníku serveru

Stiskněte klávesu **Ctrl**+**Alt**+**S** otevřete **Průzkumníka serveru**. Vyberte **Azure** ikonu a když jste rozšiřuje by měl zobrazit dostupné prostředky v účtu Azure, který je přidružen ID, které jste použili k přihlášení sadě Visual Studio. Mělo by se zobrazit přibližně takto (kromě toho, že se zobrazí vaše vlastní prostředky).

![Rozbalit uzel nástroje Azure znázorňující Průzkumníka serveru](../ide/media/vs2015_serverexplorer.png)

Při prvním použití sady Visual Studio na určité zařízení, dialogové okno se zobrazí pouze odběrů je registrovaná pod ID, které jste přihlášení k prostředí IDE s. Můžete přístup k prostředkům pro všechny vaše účty přímo z **Průzkumníka serveru** kliknutím pravým tlačítkem na **Azure** uzel a výběr **spravovat a odběry filtru**a přidání vaše účty z ovládacího prvku pro výběr účtu. Potom můžete jiný účet, v případě potřeby, kliknutím na šipku dolů a výběr ze seznamu účtů. Po výběru účet, můžete zvolit, které odběry pod tímto účtem, který chcete zobrazit v **Průzkumníka serveru**.

![Dialogové okno předplatných Azure spravovat](../ide/media/vs2015_manage_subs.png)

Při příštím otevření **Průzkumníka serveru**, jsou zobrazeny prostředky pro tento odběry.

### <a name="access-your-azure-account-via-add-connected-service-dialog"></a>Přístup k účtu Azure přes dialogové okno Přidat připojení služby

1. Vytvořte projekt aplikace UPW v jazyce C#.

1. Vyberte uzel projektu v **Průzkumníku řešení** a potom zvolte **přidat** > **připojení službě**. **Přidat připojení službě** průvodce se zobrazí a zobrazí seznam služeb v účtu Azure, která souvisí s vaším ID sady Visual Studio přihlášení. Všimněte si, že nemáte samostatně přihlaste k Azure. Však nutné se přihlásit k jiné účty při prvním pokusu o přístup k jejich prostředkům z jednoho počítače.

    > [!WARNING]
    > Pokud je to poprvé vytvoříte aplikaci UWP v sadě Visual Studio v určitém počítači, zobrazí se výzva tak, aby vaše zařízení pro režimu pro vývoj přechodem na **nastavení** > **aktualizace a zabezpečení**  >  **Pro vývojáře** ve vašem počítači. Další informace najdete v tématu [povolit zařízení pro vývoj](/windows/uwp/get-started/enable-your-device-for-development).

### <a name="access_azure"></a> Přístup k Azure Active Directory ve webovém projektu

Azure AD umožňuje podporu pro koncového uživatele jednom přihlášení do webových aplikací ASP.NET MVC nebo ověřování AD v webového rozhraní API služby. Ověřování v doméně se liší od účtu ověřování jednotlivých uživatelů; Uživatelé, kteří mají přístup k vaší doméně služby Active Directory můžete použít své stávající účty Azure AD pro připojení k vaší webové aplikace. Aplikace Office 365 můžete také použít ověřování v doméně. Toto zobrazíte v akci vytvoření webové aplikace (**soubor** > **nový projekt** > **C#** > **cloudu**  >  **Webové aplikace ASP.NET**). V **nový projekt ASP.NET** dialogovém okně, vyberte **změna ověřování**. Průvodce ověřování se zobrazí a umožní vám vybrat jaký typ ověřování pro použití ve vaší aplikaci.

![Změna ověřovací dialog pro technologii ASP.NET](../ide/media/vs2015_change_authentication.png)

Další informace o různých druhů ověřování v technologii ASP.NET najdete v tématu [webové projekty ASP.NET vytvořit v sadě Visual Studio 2013](http://www.asp.net/visual-studio/overview/2013/creating-web-projects-in-visual-studio#orgauth) (informace o ověřování je stále relevantní pro aktuální verze sady Visual Studio).

### <a name="access-your-visual-studio-team-services-account"></a>Přístup k účtu Visual Studio Team Services

Z hlavní nabídky zvolte **Team** > **připojit k serveru Team Foundation Server** se zprovoznit **Team Explorer** okno. Klikněte na **vyberte týmové projekty**a potom v seznamu v části **vyberte Team Foundation Server**, měli byste vidět adresu URL pro váš účet Visual Studio Team Services. Když vyberete adresa URL bude být přihlášení bez nutnosti znovu zadejte své přihlašovací údaje.

## <a name="add-a-second-user-account-to-visual-studio"></a>Druhý uživatelský účet přidal k sadě Visual Studio

Klikněte na šipku dolů vedle vašeho jména uživatele v horním rohu sady Visual Studio. Zvolte **nastavení účtu** položku nabídky. **Správce účtu** se zobrazí dialogové okno a zobrazí účet jste se přihlásili. Vyberte **přidat účet** odkaz v dolním rohu dialogu přidat nový účet Microsoft nebo o nový pracovní nebo školní účet.

![Výběr účtu služby Visual Studio](../ide/media/vs2015_acct_picker.png)

Postupujte podle pokynů zadejte nová pověření pro účet. Následující obrázek ukazuje **správce účtu** po jeho přidání uživatele *Contoso.com* pracovní účet.

![Účet správce](../ide/media/vs2015_accountmanager.gif)

## <a name="revisit-the-add-connected-services-wizard-and-server-explorer"></a>Pokroku průvodce Přidat připojení služby a Průzkumníka serveru

Nyní přejděte na **Průzkumníka serveru** znovu, klikněte pravým tlačítkem na **Azure** uzel a zvolte **spravovat a filtr předplatných**. Zvolte nový účet kliknutím šipku rozevíracího seznamu vedle aktuálního účtu a potom vyberte předplatné, které chcete zobrazit v **Průzkumníka serveru**. Měli byste vidět všechny služby, které jsou přidružené k zadanému odběru. I když nejste aktuálně přihlášení k prostředí Visual Studio IDE s druhého účtu, jste přihlášeni k tomuto účtu služby a prostředky. Totéž platí pro **projektu** > **přidat připojení službě** a **Team** > **připojit k serveru Team Foundation Server**.

## <a name="see-also"></a>Viz také:

- [Přihlášení k sadě Visual Studio](signing-in-to-visual-studio.md)
