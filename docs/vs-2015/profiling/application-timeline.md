---
title: Časová osa aplikace | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: df7d854b-0a28-45a9-8a64-c015a4327701
caps.latest.revision: 15
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 0f899e081377ecc1a56e141f8793d6f707df2b69
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "85534079"
---
# <a name="application-timeline"></a>Časová osa aplikace
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Pomocí nástroje **Časová osa aplikace** Profiler můžete vyhledat a opravit související problémy s výkonem v aplikacích XAML v interakci s aplikací. Tento nástroj pomáhá zlepšit výkon aplikací XAML tím, že poskytuje podrobné zobrazení využití prostředků aplikací. Můžete analyzovat čas strávený vaší aplikací při přípravě rámců uživatelského rozhraní (rozložení a vykreslování), obsluhování síťových a diskových požadavků a ve scénářích, jako je spuštění aplikace, načítání stránky a změna velikosti oken.  
  
 **Časová osa aplikace** je jedním z nástrojů, které můžete spustit pomocí příkazu **Debug/Performance Profiler...** .  
  
 Tento nástroj nahrazuje nástroj **rychlost odezvy UI XAML** , který byl součástí diagnostické sady nástrojů pro Visual Studio 2013.  
  
 Tento nástroj můžete použít na následujících platformách:  
  
1. Univerzální aplikace pro Windows (ve Windows 10)  
  
2. Windows Store 8.1   
  
3. Windows Phone 8,1 (Common XAML Platform)  
  
4. Windows Presentation Foundation (.NET 4,0 a vyšší)  
  
5. Windows 7  
  
> [!NOTE]
> Můžete shromažďovat a analyzovat data o využití procesoru a údaje o spotřebě energie společně s **ApplicationTimeline** daty. Viz [spuštění nástrojů pro profilaci bez ladění](https://msdn.microsoft.com/library/e97ce1a4-62d6-4b8e-a2f7-61576437ff01) .  
  
## <a name="collect-application-timeline-data"></a><a name="BKMK_Collect_Timeline_data_for_your_app"></a> Shromažďovat data Časová osa aplikace  
 Můžete profilovat rychlost odezvy vaší aplikace na místním počítači, připojeném zařízení, simulátoru nebo emulátorech sady Visual Studio nebo na vzdáleném zařízení. Viz [spuštění nástrojů pro profilaci bez ladění](https://msdn.microsoft.com/library/e97ce1a4-62d6-4b8e-a2f7-61576437ff01).  
  
> [!TIP]
> Pokud je to možné, spusťte aplikaci přímo na zařízení. Výkon aplikace zjištěný simulátorem nebo prostřednictvím připojení ke vzdálené ploše nemusí být stejný jako skutečný výkon na zařízení. Na druhé straně shromažďování dat pomocí nástrojů Visual Studio Remote Tools nemá vliv na data výkonu.  
  
 Zde jsou základní kroky:  
  
1. Otevřete aplikaci XAML.  
  
2. Klikněte na **ladění/Profiler výkonnosti...**. V okně. diagsession by se měl zobrazit seznam nástrojů pro profilaci.  
  
3. Vyberte **Časová osa aplikace** a potom v dolní části okna klikněte na tlačítko **Spustit** .  
  
    > [!NOTE]
    > Může se zobrazit okno Řízení uživatelských účtů požadující vaše oprávnění ke spuštění VsEtwCollector.exe. Klikněte na **Ano**.  
  
4. Pokud chcete shromažďovat údaje o výkonu, spusťte scénář, který vás zajímá při profilaci ve vaší aplikaci.  
  
5. Pokud chcete profilaci zastavit, přepněte zpátky do okna. diagsession a v horní části okna klikněte na **zastavit** .  
  
     Aplikace Visual Studio analyzuje shromážděná data a zobrazuje výsledky.  
  
     ![Sestava profileru časové osy](../profiling/media/timeline-base.png "TIMELINE_Base")  
  
## <a name="analyze-timeline-profiling-data"></a><a name="BKMK_Analyze_Timeline_profiling_data"></a> Analýza dat profilace časových os  
 Chcete-li spustit analýzu, řiďte se po shromáždění profilačních dat těmito kroky:  
  
1. Zkontrolujte informace v grafech **využití vlákna UI** a **Vizuální propustnost (FPS)** a pak pomocí navigačních panelů pro časovou osu vyberte časový rozsah, který chcete analyzovat.  
  
2. Pomocí informací v grafech **využití vlákna uživatelského rozhraní** nebo **Vizuální propustnost (FPS)** zkontrolujte podrobnosti v zobrazení **Details Timeline** , abyste zjistili možné příčiny nedostatečné odezvy.  
  
### <a name="report-scenarios-categories-and-events"></a><a name="BKMK_Report_scenarios_categories_and_events"></a> Scénáře, kategorie a události sestav  
 Nástroj **Časová osa aplikace** zobrazuje data časování pro scénáře, kategorie a události, které souvisejí s výkonem XAML.  
  
### <a name="diagnostic-session-timeline"></a><a name="BKMK_Diagnostic_session_timeline"></a> Časová osa relace diagnostiky  
 ![Časová osa výkonu a diagnostiky](../profiling/media/diaghub-timelinewithusermarks.png "DIAGHUB_TimelineWithUserMarks")  
  
 Pravítko v horní části stránky zobrazuje časovou osu pro profilované informace. Tato časová osa se vztahuje na graf **využití vlákna uživatelského rozhraní** i na graf pro **Vizuální propustnost** . Přetažením navigačních panelů na časové ose můžete vybrat určitou část časové osy a zúžit tak rozsah sestavy.  
  
 Na časové ose se také zobrazují všechny uživatelské značky, které jste tam vložili, a události z aktivačního životního cyklu aplikace.  
  
### <a name="ui-thread-utilization-graph"></a><a name="BKMK_UI_thread_utilization_graph"></a> Graf využití vlákna uživatelského rozhraní  
 ![Graf využití procesoru](../profiling/media/timeline-cpuutilization.png "TIMELINE_CpuUtilization")  
  
 Graf **využití vlákna UI (%)** je pruhový graf, který zobrazuje relativní dobu strávenou v kategorii pro v rámci rozsahu kolekce.  
  
### <a name="visual-throughput-fps-graph"></a><a name="BKMK_Visual_throughput_FPS_graph"></a> Graf vizuální propustnost (FPS)  
 ![Graf propustnosti vizuálů](../profiling/media/timeline-visualthroughput.png "TIMELINE_VisualThroughput")  
  
 Spojnicový graf **Vizuální propustnost (FPS)** zobrazuje počet snímků za sekundu (FPS) v uživatelském rozhraní a vlákně kompozice pro aplikaci.  
  
### <a name="timeline-details"></a><a name="BKMK_Timeline_details_"></a> Podrobnosti časové osy  
 V zobrazení podrobností je místo, kde budete vykazovat většinu času analýzou sestavy. Zobrazuje podrobné zobrazení využití procesoru vaší aplikace, které je rozdělené do kategorií pomocí subsystému uživatelského rozhraní nebo systémové součásti, která CPU využila.  
  
 Podporují se tyto události:  
  
|Název|Popis|  
|-|-|  
|**Analýze**|Čas strávený analýzou souborů XAML a vytváření objektů<br /><br /> Rozbalením uzlu **analýzy** v **podrobnostech časové osy** se zobrazí řetězec závislosti všech souborů XAML, které byly analyzovány jako výsledek kořenové události. To vám umožní identifikovat nepotřebnou analýzu souborů a vytvoření objektu ve scénářích citlivých na výkon a optimalizovat.|  
|**Rozložení**|Ve velkých aplikacích lze na obrazovce zobrazit tisíce prvků současně. Výsledkem může být frekvence snímků s nízkým uživatelským rozhraním a odpovídající nedostatečná odezva aplikace. Událost rozložení přesně určuje náklady na rozložení každého prvku (tj. čas strávený při uspořádání, měření, ApplyTemplate, ArrangeOverride a ArrangeOverride) a sestaví vizuální stromy, které byly součástí průchodu rozložení. Tuto vizualizaci můžete použít k určení, které z vašich logických stromů vyžaduje vyřazení, nebo k vyhodnocení jiných mechanismů odložení za účelem optimalizace úspěšnosti rozložení.|  
|**Vykreslování**|Čas strávený vykreslováním prvků XAML na obrazovce|  
|**I/0**|Čas strávený načítáním dat z místního disku nebo ze síťových prostředků, které jsou dostupné prostřednictvím [rozhraní Microsoft Windows Internet (WinInet) API](https://msdn.microsoft.com/library/windows/desktop/aa385331.aspx).|  
|**Kód aplikace**|Čas strávený prováděním kódu aplikace (uživatele), který nesouvisí s analýzou nebo rozložením.|  
|**XAML – ostatní**|Čas strávený spouštěním kódu XAML runtime.|  
  
> [!TIP]
> Když spustíte profilování pro zobrazení metod aplikace, které se spouštějí ve vlákně uživatelského rozhraní, vyberte nástroj **využití CPU** společně s nástrojem **Časová osa aplikace** . Přesun dlouhotrvajícího kódu aplikace do vlákna na pozadí může zlepšit rychlost odezvy uživatelského rozhraní.  
  
#### <a name="customizing-timeline-details"></a><a name="BKMK_Customizing_Timeline_details_"></a> Přizpůsobení podrobností časové osy  
 Pomocí panelu nástrojů **Podrobnosti časové osy** můžete seřadit, filtrovat a zadat poznámky k **podrobnostem zobrazení na časové ose** .  
  
|Název|Popis|  
|-|-|  
|**Seřadit podle**|Seřaďte data podle času zahájení nebo délky událostí.|  
|![Seskupit události podle rámce](../profiling/media/timeline-groupbyframes.png "TIMELINE_GroupByFrames")|Přidá nebo odebere kategorii **rámce** nejvyšší úrovně, která seskupuje události podle rámce.|  
|![Filtrovat seznam podrobností časové osy](../profiling/media/timeline-filter.png "TIMELINE_Filter")|Vyfiltruje seznam podle vybraných kategorií a délky událostí.|  
|![Přizpůsobení informací o podrobnostech časové osy](../profiling/media/timeline-viewsettings.png "TIMELINE_ViewSettings")|Umožňuje zadat poznámky pro události.|  
  
## <a name="see-also"></a>Viz také  
 [Blog týmu WPF: nový nástroj pro analýzu výkonu uživatelského rozhraní pro aplikace WPF](https://devblogs.microsoft.com/wpf/new-ui-performance-analysis-tool-for-wpf-applications/)   
 [Osvědčené postupy výkonu pro aplikace pro Windows Store využívající C++, C# a Visual Basic](https://msdn.microsoft.com/567bcefa-5da5-4e42-a4b8-1358c71adfa2)   
 [Optimalizace výkonu aplikace WPF](https://msdn.microsoft.com/library/ac8c6aa3-3c68-4a24-9827-3b6c829c1ebf)
