---
title: Tipy pro výkon | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 509d2d4f-48a5-4cdf-acad-6f7b75421303
caps.latest.revision: 11
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 5177add88897a838b95b6ca2aff94e03bc9e3509
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54763490"
---
# <a name="perftips"></a>Tipy pro výkon
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Ladicí program sady Visual Studio *tipy pro výkon* a integrovaný ladicí program **diagnostické nástroje** dozvíte, jak monitorovat a analyzovat výkon vaší aplikace během ladění.  
  
 I když diagnostické nástroje integrované v ladicím programu jsou skvělý způsob, od zjištění problémů s výkonem při vývoji, ladicí program může mít významný dopad na výkon vaší aplikace. Ke shromažďování přesnější údaje o výkonu, zvažte použití diagnostických nástrojů sady Visual Studio, na kterých běží mimo ladicí program příliš jako další část vaší vyšetřování výkonu. Zobrazit [spustit profilovací nástroje bez ladění](http://msdn.microsoft.com/library/e97ce1a4-62d6-4b8e-a2f7-61576437ff01).  
  
## <a name="perftips"></a>Tipy pro výkon  
 Pokud ladicí program zastaví provedení u zarážky a krokování operace, uplynulý čas přerušení od předchozí zarážky se zobrazí jako popis tlačítka v okně editoru. Další informace najdete v tématu [tipy pro výkon: Výkon informace na přehledem při ladění se sadou Visual Studio](http://blogs.msdn.com/b/visualstudioalm/archive/2014/08/18/perftips-performance-information-at-a-glance-while-debugging-with-visual-studio.aspx).  
  
 ![PerfTip](../profiling/media/dbgdiag-perf-perftip.png "DBGDIAG_PERF_PerfTip")  
  
## <a name="diagnostics-tools-window"></a>Okno diagnostické nástroje  
 Zarážky a údaje o načasování přidružených dat časování jsou zaznamenány v okně diagnostické nástroje  
  
 Následující obrázek znázorňuje okno diagnostické nástroje ve Visual Studio 2015 Update 1:  
  
 ![DiagnosticTools&#45;Update1](../profiling/media/diagnostictools-update1.png "DiagnosticTools-Update1")  
  
-   **Události přerušení** časová osa označit zarážky, které se dosáhlo v relaci ladění. Klikněte na událost, která ho vyberte **ladicí program** seznam podrobností.  
  
-   **Využití výkonu procesoru** graf zobrazuje změnu ve využití procesoru ze všech jader procesoru v relaci ladění.  
  
-   **Události** seznam **ladicí program** v podokně podrobností zahrnují položky pro každou událost přerušení.  
  
-   **Doba trvání** sloupec události přerušení Zobrazí uplynulý čas mezi událostí a předchozí zarážky.  
  
## <a name="turn-perftips-on-or-off"></a>Zapnout nebo vypnout tipy pro výkon  
 K povolení nebo zakázání tipy pro výkon:  
  
1.  Na **ladění** nabídce zvolte **možnosti**.  
  
2.  Zaškrtněte nebo zrušte zaškrtnutí **zobrazit vypršel PerfTip při ladění**.  
  
## <a name="turn-the-diagnostic-tools-window-on-or-off"></a>Zapnout nebo vypnout v okně diagnostické nástroje  
 Povolit nebo zakázat v okně diagnostické nástroje:  
  
1.  Na **ladění** nabídce zvolte **možnosti**.  
  
2.  Zaškrtněte nebo zrušte zaškrtnutí **při ladění povolit diagnostické nástroje**.
