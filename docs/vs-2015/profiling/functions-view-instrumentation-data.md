---
title: Zobrazení funkcí – data instrumentace | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- Function view
ms.assetid: 595d91c8-a42b-4644-85b8-39e8140a5dfe
caps.latest.revision: 16
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: ef2375fc4132e0274e7cded6daf5bdd0a58891c4
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "62580222"
---
# <a name="functions-view---instrumentation-data"></a>Zobrazení funkcí – data instrumentace
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

V zobrazení sestavy funkce jsou uvedena data profilace podle názvu funkce.  
  
## <a name="general"></a>Obecné  
 Obecné sloupce identifikují funkci v řádku zobrazení.  
  
|Sloupec|Popis|  
|------------|-----------------|  
|**Název funkce**|Název funkce|  
|**Adresa funkce**|Adresa funkce|  
|**Číslo řádku funkce**|Číslo řádku začátku této funkce ve zdrojovém souboru.|  
|**Number of Calls**|Celkový počet volání této funkce.|  
|**Zdrojový soubor**|Zdrojový soubor obsahující definici této funkce|  
|**Název modulu**|Název modulu, který obsahuje funkci.|  
|**Cesta k modulu**|Cesta modulu, který obsahuje funkci.|  
|**ID procesu**|ID procesu (PID) pro spuštění profilace.|  
|**Název procesu**|Název procesu|  
|**Výhradní čas režie testu**|Časová režie této funkce, která je způsobena instrumentací. Nezahrnuje režijní náklady ve funkcích, které byly volány funkcí. Režie testu byla odečtena od všech výhradních časů.|  
|**Čas celkové režie testu**|Časová režie této funkce a jejích podřízených funkcí, které jsou způsobeny instrumentací. Zahrnuje režii ve funkcích, které byly volány funkcí. Režie testu byla odečtena od všech celkových časů.|  
  
## <a name="elapsed-inclusive-values"></a>Uplynulé celkové hodnoty  
 Uplynulé celkové hodnoty udávají čas, kdy byla funkce v zásobníku volání. Čas zahrnuje čas strávený ve funkcích, které byly volány funkcí a časem stráveným voláním do operačního systému, jako jsou například přepínače kontextu a vstupně-výstupní operace.  
  
|Sloupec|Popis|  
|------------|-----------------|  
|**Uplynulý celkový čas**|Celkový uplynulý celkový čas všech volání této funkce.|  
|**% Uplynulého celkového času**|Procento celkového uplynulého celkového času běhu profilace, které bylo stráveno v uplynulém celkovém čase této funkce.|  
|**Průměrný uplynulý celkový čas**|Průměrně uplynulý celková doba volání této funkce.|  
|**Maximální uplynulý celkový čas**|Maximální uplynulý celková doba volání této funkce.|  
|**Minimální uplynulý celkový čas**|Minimální uplynulý celkový čas volání této funkce.|  
  
## <a name="elapsed-exclusive-values"></a>Uplynulé výhradní hodnoty  
 Uplynulé výhradní hodnoty označují čas, kdy funkce prováděla kód v těle funkce, to znamená, když byla funkce v horní části zásobníku volání. Čas zahrnuje čas strávený voláním do operačního systému, jako jsou například přepínače kontextu a vstupně-výstupní operace, ale nezahrnuje čas strávený ve funkcích, které byly volány funkcí.  
  
|Sloupec|Popis|  
|------------|-----------------|  
|**Uplynulý výhradní čas**|Celkový uplynulý výhradní čas všech volání této funkce.|  
|**% Uplynulého výhradního času**|Procento celkového uplynulého výhradního času pro spuštění profilování, které bylo stráveno celkovým uplynulým výhradním časem této funkce.|  
|**Průměrný uplynulý výhradní čas**|Průměrný uplynulý výhradní čas volání této funkce.|  
|**Maximální uplynulý výhradní čas**|Maximální uplynulý výhradní čas volání této funkce.|  
|**Minimální uplynulý výhradní čas**|Minimální uplynulý výhradní čas volání této funkce.|  
  
## <a name="application-inclusive-values"></a>Hodnoty zahrnující aplikace  
 Hodnoty pro všechny aplikace označují čas, kdy byla funkce v zásobníku volání. Čas neobsahuje čas strávený voláním operačního systému, jako jsou například přepínače kontextu a vstupně-výstupní operace, ale obsahuje čas strávený ve funkcích, které byly volány funkcí.  
  
|Sloupec|Popis|  
|------------|-----------------|  
|**Celková doba aplikace**|Celkový čas všech volání této funkce pro všechny aplikace.|  
|**% Celkového času aplikace**|Procento celkového uplynulého celkového času běhu profilace, které bylo stráveno v celkovém čase aplikace této funkce.|  
|**Průměrná doba aplikace (celková)**|Průměrná doba použití volání této funkce.|  
|**Maximální celková doba aplikace**|Maximální doba volání této funkce v rámci aplikace.|  
|**Minimální celková doba aplikace**|Minimální doba pro volání této funkce (včetně celkového počtu aplikací).|  
  
## <a name="application-exclusive-values"></a>Exkluzivní hodnoty aplikací  
 Hodnoty exkluzivní pro aplikace označují čas, kdy byla funkce přímo spuštěna v horní části zásobníku volání. Čas neobsahuje čas strávený voláním operačního systému, jako jsou například přepínače kontextu a vstupně-výstupní operace, a neobsahuje čas strávený ve funkcích, které byly volány funkcí.  
  
|Sloupec|Popis|  
|------------|-----------------|  
|**Výhradní čas aplikace**|Celkový výhradní čas všech volání této funkce.|  
|**% Výhradního času aplikace**|Procento celkového uplynulého výhradního času spuštění profilování, které bylo stráveno v celkovém čase aplikace, který je výhradně členem této funkce.|  
|**Průměrný výhradní čas aplikace**|Průměrná doba aplikace, která je výhradním časem pro volání této funkce.|  
|**Maximální výhradní čas aplikace**|Maximální doba výhradního volání této funkce pro aplikaci.|  
|**Minimální výhradní čas aplikace**|Minimální výhradní čas aplikace pro volání této funkce.|  
  
## <a name="see-also"></a>Viz také  
 [Postupy: přizpůsobení sloupců zobrazení sestavy](../profiling/how-to-customize-report-view-columns.md)   
 [Zobrazení funkcí](../profiling/functions-view-sampling-data.md)   
 [Zobrazení funkcí – vzorkování](../profiling/functions-view-dotnet-memory-sampling-data.md)   
 [Zobrazení funkcí – instrumentace](../profiling/functions-view-dotnet-memory-instrumentation-data.md)
