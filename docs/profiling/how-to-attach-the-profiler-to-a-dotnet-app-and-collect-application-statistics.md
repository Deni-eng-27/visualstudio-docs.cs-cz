---
title: 'Postupy: připojení profileru k samostatné aplikaci .NET Framework a shromažďování statistik aplikace pomocí příkazového řádku | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: b62fcbc1-791f-474e-890a-a6c332e0c9ea
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 5912e6704a50884df2000afb7c12f82f7a8aa69f
ms.sourcegitcommit: 046a9adc5fa6d6d05157204f5fd1a291d89760b7
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/11/2018
---
# <a name="how-to-attach-the-profiler-to-a-net-framework-stand-alone-application-and-collect-application-statistics-by-using-the-command-line"></a>Postupy: Připojení profileru k samostatné aplikaci .NET Framework a shromažďování statistik aplikace pomocí příkazového řádku
Toto téma popisuje postup použití [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] profilace nástroje příkazového řádku nástroje pro připojení profileru k aplikaci spuštěné samostatné (klient) rozhraní .NET Framework a shromažďování statistik výkonu pomocí metody vzorkování.  
  
> [!NOTE]
>  Funkce Rozšířené zabezpečení v systému Windows 8 a Windows Server 2012 vyžaduje významné změny ve způsobu, jakým Visual Studio profiler shromažďuje data na těchto platformách. Aplikace UWP také vyžadují nové techniky kolekce. V tématu [nástroje pro sledování výkonu v aplikacích pro Windows 8 a Windows Server 2012](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
>   
>  Nástroje příkazového řádku nástroje profilace jsou umístěny v podadresáři nástroje \Team Tools\Performance [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] instalační adresář. Na 64bitových počítačích 64bitové a 32bitové verze nástroje jsou k dispozici. Chcete-li použít nástroje příkazového řádku profileru, musí přidat cestu nástroje do proměnné prostředí PATH okna příkazového řádku nebo ho přidat do samotný příkaz. Další informace najdete v tématu [určení cesty k nástrojům příkazového řádku](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).  
>   
>  Přidání dat interakce vrstev pro spuštění profilování vyžaduje konkrétní postupy s příkazového řádku nástroje pro profilaci. V tématu [shromažďování dat interakce vrstev](../profiling/adding-tier-interaction-data-from-the-command-line.md).  
  
 Ke shromažďování dat výkonu z aplikace rozhraní .NET Framework, příslušné proměnné prostředí je nutné inicializovat před spuštěním cílové aplikace. Po připojení profileru k aplikaci, můžete pozastavit a obnovit data kolekce.  
  
 K ukončení relace profilování, musí být už připojené profileru k aplikaci a profileru musí být explicitně vypnuté. Ve většině případů doporučujeme vymazání profilování proměnné prostředí na konci relace profilování.  
  
## <a name="attaching-the-profiler"></a>Připojení profileru  
  
#### <a name="to-attach-the-profiler-to-a-running-net-framework-application"></a>Chcete-li připojení profileru k spuštěné aplikace rozhraní .NET Framework  
  
1.  Otevřete okno příkazového řádku.  
  
2.  Inicializujte profilování proměnné prostředí. Typ:  
  
     **Vsperfclrenv – /sampleon** [**/samplelineoff**]  
  
    -   **/Samplelineoff** možnost zakáže shromažďování dat o zdrojovém kódu řádku číslo.  
  
3.  Spusťte profileru. Typ:  
  
     **VSPerfCmd /start:sample output:** `OutputFile` [`Options`]  
  
    -   [/Start](../profiling/start.md)**: Ukázka** možnost inicializuje profileru.  
  
    -   [/Výstup](../profiling/output.md)**:** `OutputFile` možnost je povinná s **/start**. `OutputFile` Určuje název a umístění souboru profilování dat (.vsp).  
  
     Můžete použít některou z následujících možností s **/start:sample** možnost.  
  
    |Možnost|Popis|  
    |------------|-----------------|  
    |[Parametr/User](../profiling/user-vsperfcmd.md) **:**[`Domain`**\\**]`UserName`|Určuje nepovinné doména a uživatelské jméno účtu, který vlastní PROFILOVANÉHO proces. Tato možnost je povinná, pouze v případě, že PROFILOVANÉHO aplikace byla spuštěna jako uživatel, než je přihlášený uživatel.|  
    |[/crosssession](../profiling/crosssession.md)|Umožňuje profilace procesů v jiných relacích přihlášení. **/CS** lze zadat jako zkratkou pro **/crosssession**. Tato možnost je povinná, pokud je aplikace spuštěna v jiné relaci.|  
    |[/wincounter](../profiling/wincounter.md) **:** `WinCounterPath`|Určuje čítačů výkonu systému Windows, které se mají shromažďovat při vytváření profilu.|  
    |[/automark](../profiling/automark.md) **:** `Interval`|Použití s **/wincounter** pouze. Určuje počet milisekund, po mezi události kolekce čítače výkonu systému Windows. Výchozí hodnota je 500 ms.|  
    |[/Events](../profiling/events-vsperfcmd.md) **:** `Config`|Určuje událost trasování událostí pro Windows (ETW), které se mají shromažďovat při vytváření profilu. Události trasování událostí se shromažďují v souboru samostatné (ETL).|  
  
4.  V případě potřeby spusťte cílová aplikace typické způsobem.  
  
5.  Připojení profileru k cílové aplikaci. Typ:  
  
     **VSPerfCmd / připojit:**{`PID`&#124;`ProcessName`} [`Sample Event`] [**/targetclr:**`Version`]  
  
    -   `PID` Určuje ID procesu cílová aplikace. `ProcessName` Určuje název procesu. Všimněte si, že pokud zadáte `ProcessName` a více procesy, které mají stejný název běží, výsledky mohou být nepředvídatelné. Proces ID všechny spuštěné procesy můžete zobrazit ve Správci úloh systému Windows.  
  
    -   [/targetclr](../profiling/targetclr.md) **:** `Version` určuje verzí common language runtime (CLR) má profil při načtení více než jednu verzi modulu runtime v aplikaci. Volitelné.  
  
    -   Ve výchozím nastavení, data výkonu vzorkovat hodin každých 10 000 000-zastavit procesoru cykly. Toto je přibližně jednou každých 10 sekund 1GH procesoru. Můžete zadat jednu z následujících možností změnit interval cyklus hodiny nebo zadejte jiný vzorkování událostí. [/targetclr](../profiling/targetclr.md)**:** `Version` Určuje verzi modulu CLR do profilu při načtení více než jednu verzi modulu runtime v aplikaci. Volitelné.  
  
    |||  
    |-|-|  
    |Událost vzorku|Popis|  
    |[/Timer](../profiling/timer.md) **:** `Interval`|Interval vzorkování se změní na počet cyklů-Zastavit hodiny, které jsou určené `Interval`.|  
    |[/PF](../profiling/pf.md) [**:**`Interval`]|Změny událostí vzorkování chyb stránek. Pokud `Interval` je zadané, nastaví počet chyb stránek mezi vzorky. Výchozí hodnota je 10.|  
    |[/ sys](../profiling/sys-vsperfcmd.md) [**:**`Interval`]|Změny událostí vzorkování systémová volání z procesu s jádrem operačního systému (syscalls). Pokud `Interval` je zadané, nastaví počet volání mezi vzorky. Výchozí hodnota je 10.|  
    |[/ Čítač](../profiling/counter.md) **:** `Config`|Změny událostí vzorkování a intervalu čítače výkonu procesoru a interval, který jsou určené v `Config`.|  
  
    -  
  
## <a name="controlling-data-collection"></a>Řízení kolekce dat  
 Pokud cílová aplikace běží, lze řídit shromažďování dat spuštění a zastavení zápisu dat do datového souboru profileru pomocí **VSPerfCmd.exe** možnosti. Řízení shromažďování dat umožňuje shromažďování dat pro konkrétní součást spuštění programu, jako je například spouštění nebo ukončením aplikace.  
  
#### <a name="to-start-and-stop-data-collection"></a>Spuštění a zastavení shromažďování dat  
  
-   Následující páry možnosti spuštění a zastavení shromažďování dat. Zadejte jednotlivé možnosti na samostatném řádku příkaz. Shromažďování dat můžete zapnout a vypnout vícekrát.  
  
    |Možnost|Popis|  
    |------------|-----------------|  
    |[/globalon /globaloff](../profiling/globalon-and-globaloff.md)|Spustí (**/globalon**) nebo zastaví (**/globaloff**) shromažďování dat pro všechny procesy.|  
    |[/processon](../profiling/processon-and-processoff.md) **:** `PID` [/processoff](../profiling/processon-and-processoff.md) **:** `PID`|Spustí (**/processon**) nebo zastaví (**/processoff**) shromažďování dat pro proces, který je zadán `PID`.|  
    |[/ připojit](../profiling/attach.md) **:**{`PID`&#124;`ProcName`} [/ detach](../profiling/detach.md)[**:**{`PID`&#124;`ProcName`}]|**/ připojit** spustí ke shromažďování dat pro proces, který je zadán `PID` nebo název procesu (Nazev_procedury). **/ detach** zastaví shromažďování dat pro zadaný procesu nebo pro všechny procesy, pokud není zadán konkrétní proces.|  
  
## <a name="ending-the-profiling-session"></a>Ukončení relace profilování  
 K ukončení relace profilování, musí být profileru odpojit od všech PROFILOVANÉHO procesů a profileru musí být explicitně vypnuté. Můžete odpojit profileru z aplikace, která byla profilovaným pomocí metody vzorkování ukončením aplikace nebo voláním **VSPerfCmd / detach** možnost. Potom zavolejte **/VSPerfCmd Shutdown** možnost vypnout profileru a zavřete profilování datového souboru. **Vsperfclrenv – / vypnuto** příkaz vymaže profilování proměnné prostředí.  
  
#### <a name="to-end-a-profiling-session"></a>K ukončení relace profilování  
  
1.  Proveďte jeden z následujících kroků k odpojení profileru z cílová aplikace:  
  
    -   Typ **VSPerfCmd / odpojit**  
  
         -nebo-  
  
    -   Zavřete cílová aplikace.  
  
2.  Vypněte profileru. Typ:  
  
     **VSPerfCmd** [ /Shutdown](../profiling/shutdown.md)  
  
3.  (Volitelné) Zrušte profilování proměnné prostředí. Typ:  
  
     **Vsperfclrenv – / vypnuto**  
  
## <a name="see-also"></a>Viz také  
 [Profilace samostatných aplikací](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Zobrazení dat metody vzorkování](../profiling/profiler-sampling-method-data-views.md)