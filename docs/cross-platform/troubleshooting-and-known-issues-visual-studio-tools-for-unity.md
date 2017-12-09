---
title: "Řešení potíží a známé problémy (Visual Studio Tools for Unity) | Microsoft Docs"
ms.custom: 
ms.date: 10/25/2017
ms.reviewer: 
ms.suite: 
ms.technology: tgt-pltfrm-cross-plat
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8f5db192-8d78-4627-bd07-dbbc803ac554
caps.latest.revision: "5"
author: conceptdev
ms.author: crdun
manager: crdun
ms.openlocfilehash: 338f80724598a3c89dcde3806511427b81bffca4
ms.sourcegitcommit: ebe9fb5eda724936f7a059d35d987c29dffdb50d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/07/2017
---
# <a name="troubleshooting-and-known-issues-visual-studio-tools-for-unity"></a>Odstraňování potíží a známé problémy (Visual Studio Tools for Unity)
V této části najdete řešení pro běžné problémy s nástroji Visual Studio Tools for Unity, popisem známých problémů a zjistěte, jak můžete pomocí Visual Studio Tools for Unity zlepšit zasílání zpráv o chybách.  

## <a name="troubleshooting"></a>Poradce při potížích  
Chcete-li vyřešit některé běžné problémy s nástroji Visual Studio Tools for Unity, najdete v následujících částech.  

### <a name="visual-studio-crashes"></a>Visual Studio dojde k chybě
Může to být kvůli mezipaměť Visual Studio MEF je poškozený.

Odstraňte následující složku resetovat mezipaměť MEF (před provedením této akce zavřete Visual Studio):

```batch
%localappdata%\Microsoft\VisualStudio\<version>\ComponentModelCache
```

To by měl opravit příslušný problém. V případě, že se stále setkáváte problému, spusťte příkazový řádek vývojáře pro sadu Visual Studio jako správce a použijte následující příkaz:

```batch
 devenv /setup
```

### <a name="issues-with-vs2015-and-intellisense-or-code-coloration"></a>Problémy s zabarvení VS2015 a Intellisense nebo kódu.
Pokuste se upgrade vaší Visual Studio 2015 s aktualizací 3.

### <a name="visual-studio-hangs"></a>Visual Studio přestane reagovat.
Několik modulů plug-in Unity jako analýzy, FMOD, JÍMKU (Universal Media Player), ZFBrowser nebo vložené prohlížeče používají nativní vláken. Problém je při ukončení modulů plug-in až nativní vlákno se připojuje k modul runtime, který poté provede blokování volání operačního systému. To znamená Unity nelze přerušení daném vláknu pro ladicí program (nebo opětovného načtení domény) a zablokuje.

Pro FMOD, je alternativní řešení, můžete předat FMOD_STUDIO_INIT_SYNCHRONOUS_UPDATE inicializace [příznak](https://www.fmod.org/docs/content/generated/FMOD_STUDIO_INITFLAGS.html) zakázat asynchronní zpracování a provádět veškeré zpracování na hlavní vlákno.

### <a name="incompatible-project-in-visual-studio"></a>Nekompatibilní projektu v sadě Visual Studio
Nejdřív zkontrolujte, že Visual Studio je nastaven jako externího skriptu editoru Unity (upravit/předvolby/externí nástroje). Potom zkontrolujte, že modul plug-in sady Visual Studio je nainstalován ve Unity (Nápověda/o musí zobrazí zprávu, jako je Microsoft Visual Studio Tools for Unity povoleno v dolní části). Potom zkontrolujte, zda rozšíření je správně nainstalován v sadě Visual Studio (Nápověda/o).

### <a name="assembly-reference-issues"></a>Potíže s odkazy sestavení
Pokud je váš projekt komplexní reference-wise nebo pokud chcete lépe kontrolovat, tento krok generace, můžete použít naše [rozhraní API](../cross-platform/customize-project-files-created-by-vstu.md) pro manipulaci s generovaného obsahu projekt nebo řešení. Můžete také použít [soubory odezvy](https://docs.unity3d.com/Manual/PlatformDependentCompilation.html) ve vašem Unity projektu a my vám jejich zpracování.

### <a name="breakpoints-with-a-warning"></a>Zarážky s upozorněním
Pokud Visual Studio se nepodařilo najít umístění zdroje pro konkrétní zarážek uvidíte okolo vaší zarážce upozornění. Zkontrolujte, jestli chování, které používáte správně načíst nebo použít v aktuální scény Unity.

### <a name="breakpoints-not-hit"></a>Není zarážky
 Zkontrolujte, jestli chování, které používáte správně načíst nebo použít v aktuální scény Unity. Ukončení Visual Studio a Unity pak odstraňte všechny generované soubory (*.csproj, *.sln) a celou složku knihovny.

### <a name="unable-to-attach"></a>Nelze připojit
-   Pokuste se dočasně zakázat váš antivirový nebo vytvořit pravidla vyloučení pro VS a Unity.
-   Pokuste se dočasně zakázat bránu firewall nebo vytvořit pravidla pro povolení portu TCP nebo UDP sítě mezi VS a Unity.
-   Myslíme, že programy jako prohlížeč Team narušuje proces zjišťování; případně můžete zkusit zastavit dočasně další software, pokud chcete zobrazit, pokud se změní něco.
-   Hlavní spustitelný soubor Unity nepřejmenovávejte jako VSTU pouze monitoruje procesy "Unity.exe".

### <a name="unable-to-debug-android-players"></a>Nelze k ladění Android přehrávače
Můžeme použít vícesměrové vysílání pro zjišťování player, (což je výchozí mechanismus používaný Unity), ale poté používáme regulární připojení TCP připojit ladicí program. Fáze zjišťování je hlavní problém pro zařízení s Androidem.

USB je extrémně rychlého pro ladění, ale není kompatibilní s mechanismus Unity player zjišťování.
Wi-Fi je ale super pomalé rozmanitější ve srovnání s USB z důvodu čekací doby. Jsme viděli chybějících správné podpora vícesměrového vysílání pro některé směrovače nebo zařízení (Nexus řady nejsou dobře známé pro tento).

Vyzkoušejte následující pomocí USB zobrazíte otevřené porty na připojené zařízení (s player nahoru a spuštěna, aby mohli zobrazit ladění port, vždy v 56xxx formuláře):

```shell  
adb shell netstat
```  

Budou předávány port, který se v místním počítači:

```shell  
adb forward tcp:56xxx tcp:56xxx
```  

Připojte VSTU pomocí 127.0.0.1:56xxx přesměrovaná portu.

### <a name="migrating-from-unityvs-to-visual-studio-tools-for-unity"></a>Migrace z UnityVS na Visual Studio Tools for Unity  
 Pokud se migrace z UnityVS na Visual Studio Tools for Unity, budete muset vygenerovat nové řešení sady Visual Studio pro projekty Unity.  

##### <a name="to-migrate-your-unity-project-from-unityvs-18-to-visual-studio-tools-for-unity-19"></a>Při migraci z UnityVS 1.8 projektu Unity do Visual Studio Tools pro Unity 1.9  

1.  Odstraňte staré řešení a projektu soubory z projektu Unity. V kořenovém adresáři projektu Unity, vyhledejte sadě Visual Studio .sln a. * proj soubory a odstraňte všechny.  

2.  Importujte Visual Studio Tools for Unity balíčku do projektu Unity. Informace o tom, jak importovat balíček VSTU najdete v tématu Konfigurace Visual Studio Tools for Unity na [Začínáme](../cross-platform/getting-started-with-visual-studio-tools-for-unity.md) stránky.  

3.  Generovat nové soubory řešení a projektu. Pokud chcete je generovat teď v Unity editoru v hlavní nabídce zvolte **nástroje sady Visual Studio**, **generování souborů projektu**. Jinak můžete tento krok přeskočit, pokud chcete zjistit. Visual Studio Tools for Unity vygeneruje nové soubory automaticky když zvolíte **nástroje sady Visual Studio**, **otevřete v sadě Visual Studio**.  

### <a name="on-windows-visual-studio-asks-to-download-the-unity-target-framework"></a>V systému Windows Visual Studio požádá ke stažení cílové rozhraní Unity  
 Visual Studio Tools for Unity vyžaduje rozhraní .net framework 3.5, která není nainstalovaná ve výchozím nastavení v systému Windows 8 nebo 10. Chcete-li tento problém vyřešit, postupujte podle pokynů ke stažení a instalaci rozhraní .net framework 3.5.  

## <a name="known-issues"></a>Známé problémy  
 Existují známé problémy ve Visual Studio Tools for Unity, které jsou výsledkem jak ladicí program komunikuje s Unity na starší verzi kompilátor jazyka C#. Pracujeme na řešení těchto problémů, ale může mezitím došlo k následujícím problémům:  

-   Při ladění, Unity někdy dojde k chybě.  

-   Při ladění, Unity někdy zablokuje.  

-   Krokování do a z metody někdy se chová nesprávně, zejména v iterátory nebo v příkazech switch.  

## <a name="reporting-errors"></a>Zasílání zpráv o chybách  
 Pomozte nám vylepšit kvalitu Visual Studio Tools for Unity odesílání zpráv o chybách, když dojde k chybám, zablokuje nebo jiné chyby. To pomáhá nám prozkoumat a opravte problémy v aplikaci Visual Studio Tools for Unity. Děkuju!  

### <a name="how-to-report-an-error-when-visual-studio-freezes"></a>Jak vytvářet sestavu chybu, když se zablokuje v sadě Visual Studio  
 Visual Studio v některých případech se zablokuje při ladění s nástroji Visual Studio Tools for Unity sestavy, ale potřebujeme další data tento problém pochopit. Pomůžete nám prozkoumat pomocí následujících kroků.  

##### <a name="to-report-that-visual-studio-freezes-while-debugging-with-visual-studio-tools-for-unity"></a>Pro sestavu, která se Visual Studio zablokuje při ladění s nástroji Visual Studio Tools for Unity

*V systému Windows:*  

1.  Otevření nové instance sady Visual Studio.

2.  Otevření připojení do dialogového okna procesu. V nové instanci sady Visual Studio v hlavní nabídce zvolte **ladění**, **připojit k procesu**.  

3.  Připojí ladicí program k ukotvené instanci sady Visual Studio. V **připojit k procesu** dialogovém okně, vyberte ukotvené instanci sady Visual Studio z **procesy k dispozici** tabulky, a potom vyberte **Attach** tlačítko.  

4.  Pozastavení ladicího programu. V nové instanci sady Visual Studio v hlavní nabídce zvolte **ladění**, **přerušení všech**, nebo stačí stisknout klávesu **Ctrl + Alt + Break**.  

5.  Vytvořte výpis přístup z více vláken. V okně příkazového řádku zadejte následující příkaz a stiskněte klávesu **Enter**:  

    ```powershell  
    Debug.ListCallStack /AllThreads /ShowExternalCode  
    ```  

    Budete možná muset udělat **příkaz** okno viditelné první. V sadě Visual Studio v hlavní nabídce zvolte **zobrazení**, **ostatní okna**, **příkazové okno**.  

*V systému Mac:*

1. Otevřete terminál a získat PID Visual Studio pro Mac:

    ```shell  
    ps aux | grep "[V]isual Studio.app"
    ```

1. Spuštění ladicího programu lldb:

    ```shell  
    lldb
    ```

1. Připojení k sadě Visual Studio pro Mac instanci pomocí PID:

    ```shell  
    process attach --pid THE_PID_OF_THE_VSFM_PROCESS
    ```

1. Načtení trasování zásobníku pro všechna vlákna:

    ```shell  
    bt all
    ```

Nakonec odeslat výpisu podprocesu k [ vstusp@microsoft.com ](mailto:vstusp@microsoft.com), společně s popis co jste dělali při stalo sady Visual Studio pozastaveny.
