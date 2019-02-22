---
title: 'Postupy: Nastavení oprávnění | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- profiling, setting permissions
- security [Visual Studio ALM], setting permissions
- permissions [Visual Studio ALM], profiling
- profiling tools, setting profiling permissions
- performance tools, setting profiling permissions
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e40438b6b14414371adaba6cb7eafc6377ae1187
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56620821"
---
# <a name="how-to-set-permissions"></a>Postupy: Nastavení oprávnění

Tento článek popisuje, jak správce počítače uděluje oprávněních zabezpečení pro profilaci a uživatele nebo skupiny, který nemá oprávnění správce na tomto počítači.

Princip základní zabezpečení hlásí, že aplikace má běžet s více než oprávnění, které potřebují. Tento princip platí také pro uživatele. Pokud uživatelé mohou být plně účinná, když jsou přihlášení jako členové skupiny uživatelů místo skupiny Administrators, by neměla jim udělena oprávnění správce. První postupu "postup vytvoření uživatelského účtu, který má oprávnění uživatele" popisuje, jak vytvořit uživatelský účet členem skupiny Users.

Členové skupiny uživatelů budou potřebovat přístup do složek a souborů na disku, které jsou sdíleny s ostatními členy týmu. Druhý postup "pro udělení přístupu k souborům sdíleného projektu," popisuje postup udělení tohoto přístupu.

Členové skupiny uživatelů můžete spustit nástroje pro profilaci, pokud správce udělí přístup k ovladači software pro nástrojů pro profilaci. Posledním postupu "postup udělení přístupu k ovladači profilování" popisuje, jak udělit přístup pro tento ovladač.

> [!NOTE]
> Musíte mít oprávnění správce postupovat podle kroků v těchto postupech.

## <a name="to-create-a-user-account-that-has-user-permissions"></a>Chcete-li vytvořit uživatelský účet, který má oprávnění pro uživatele

1. Klikněte pravým tlačítkem na **tento počítač** a potom klikněte na tlačítko **spravovat**.

     **Správa počítače** otevře se okno.

2. Rozbalte **místní uživatelé a skupiny**.

3. Klikněte pravým tlačítkem myši **uživatelé** složku a pak klikněte na tlačítko **nového uživatele**.

     **Nového uživatele** zobrazí se dialogové okno.

4. Vyplňte pole v tomto poli dialogové okno s informacemi pro uživatelský účet, kterou vytváříte. Zadejte heslo. V případě potřeby zaškrtněte políčko, které vyžaduje, aby uživatel změnit heslo při příštím přihlášení.

5. Klikněte na tlačítko **vytvořit** a potom klikněte na tlačítko **Zavřít**.

     Nový uživatel zobrazí ve skupině uživatelů, skupiny uživatelů, kteří nemají oprávnění správce.

## <a name="to-grant-access-to-shared-project-files"></a>K udělení přístupu k souborům sdíleného projektu

1. V Průzkumníku Windows (nebo Průzkumníka souborů) vyhledejte kořen stromu složky pro soubory projektu tento uživatel a sdílené s týmem projektu.

     Cesta této složky může vypadat takto:

    ```cmd
    D:\ourProject
    ```

2. Klikněte pravým tlačítkem na složku a potom klikněte na tlačítko **vlastnosti**.

     **\<Název složky > vlastnosti** zobrazí se dialogové okno.

3. Klikněte na tlačítko **zabezpečení** kartu.

4. Klikněte na název uživatelského účtu v **skupiny nebo jméno uživatele** pole.

5. V **oprávnění pro \<uživatelské jméno >** , vyberte zaškrtávací políčko pro **úplné řízení**.

6. Klikněte na **OK**.

     Tím udělíte oprávnění pro uživatele pro sdílené složky strom, který začíná složce vybrali v kroku 5.

## <a name="to-grant-access-to-the-profiling-driver"></a>Udělit přístup k ovladači profilování

1. Otevřete příkazový řádek jako správce.

2. Změňte adresář na:

    ```cmd
    <drive>:\Program Files\Microsoft Visual Studio 14\Team Tools\Performance Tools
    ```

3. Spusťte následující příkaz:

    ```cmd
    vsperfcmd /admin:driver,start /admin:service,start
    ```

     Tento příkaz nainstaluje a spustí ovladač nástrojů pro profilaci.

     Tento příkaz spustí profilaci ovladače a služby tak, aby uživatelům bez oprávnění správce může používat funkce profilování, které jsou k dispozici v prostoru procesu svoje uživatele. Pouze správce může spustit příkaz; a dojde k selhání pro uživatele bez oprávnění správce.

     Všimněte si, že jsou vrácena účinky tento krok po restartování počítače, pokud také provádět v posledním kroku v tomto postupu.

4. Spusťte příkaz pro povolení přístupu k profilování funkce, které uživatel nebo skupina, která nemá přístup správce k počítači:

    ```cmd
    vsperfcmd /admin:security,allow,<right[,right],<user name|group name>
    ```

     Tento příkaz udělí \<uživatelské jméno > nebo \<název skupiny > účet přístup k nástrojům profilace. \<Správné > volba určuje přístup k funkci profilování uživatele. \<Správné > možnost může být jeden nebo více z následujících hodnot:

    - FullAccess – umožňuje přístup ke shromažďování dat výkonu ze služeb, včetně všech metod profilace vzorkování a různé relace profilování.

    - SampleProfiling – umožňuje přístup k ukázkové metod profilace

    - CrossSession - umožňuje přístup pro různé relace profilování, které jsou požadovány pro profilovací služby.

5. (Volitelné) Pokud chcete zachovat výsledky některého z předchozích kroků po restartování počítače, spusťte následující příkaz:

    ```cmd
    vsperfcmd /admin:driver,autostart,on
    ```

   Zadaní uživatelé po přihlášení, teď budou moct používat profilovací nástroje bez oprávnění správce.

## <a name="see-also"></a>Viz také:

[Konfigurace výkonnostních relací](../profiling/configuring-performance-sessions.md)
[VSPerfCmd](../profiling/vsperfcmd.md)
[profilace a zabezpečení Windows Vista](../profiling/profiling-and-windows-vista-security.md)