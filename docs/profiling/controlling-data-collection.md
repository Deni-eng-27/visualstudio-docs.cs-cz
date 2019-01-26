---
title: Řízení sběru dat | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- advanced tasks for profiling tools
- profiling tools, advanced tasks
ms.assetid: e713ad63-b948-46f3-8db9-59b30922ebe5
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 32f61ab0e7922b2d7eb721fa8b50ba1fd8dd54df
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54995645"
---
# <a name="control-data-collection"></a>Řízení shromažďování dat
Nástroje pro profilaci sady [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] umožňují řídit dobu, kdy dochází během relace výkonu k profilaci dat, a slouží k určení funkcí, které jsou profilovány. Tato část popisuje, jak spustit a zastavit shromažďování dat z **prohlížeč výkonu** a **ovládacího prvku sběru dat** windows a jak omezit objekty, pro které jsou shromažďována data profilování.  
  
## <a name="common-tasks"></a>Běžné úkoly
  
|Úloha|Související obsah|  
|----------|---------------------|  
|**Spuštění a zastavení profilování:** Můžete spustit profilování aplikace při spuštění aplikace, nebo můžete připojit profiler k procesu, který je již spuštěna. Pokud je cílová aplikace spuštěna, je shromažďování dat možné pozastavit a obnovit. Ukončení relace profilování lze provést ukončením cílové aplikace nebo odpojením profileru od spuštěného procesu.|-   [Jak: Spuštění a ukončení shromažďování dat o výkonu](../profiling/how-to-start-and-end-performance-data-collection.md)<br />-   [Jak: Připojení a odpojení nástroje Sledování výkonu ke spuštěným procesům](../profiling/how-to-attach-and-detach-performance-tools-to-running-processes.md)<br />-   [Jak: Pozastavit a obnovit shromažďování údajů o výkonu](../profiling/how-to-pause-and-resume-performance-data-collection.md)|  
|**Konfigurace profilování instrumentace pro omezení sběru dat:** Vlastnosti konfigurace relace výkonu můžete omezit data, která se shromažďují v rámci profilování, které používají metodu instrumentace. Je možné zahrnout nebo vyloučit určité knihovny dll, obory názvů, třídy a funkce. Je také možné vyloučit funkce, které nesplňují zadanou mezní hodnotu velikosti.|-   [Jak: Omezení instrumentace na konkrétní knihovny DLL](../profiling/how-to-limit-instrumentation-to-specific-dlls.md)<br />-   [Jak: Omezení instrumentace na konkrétní funkce](../profiling/how-to-limit-instrumentation-to-specific-functions.md)<br />-   [Jak: Vyloučení nebo zahrnutí krátkých funkcí z instrumentace](../profiling/how-to-exclude-or-include-short-functions-from-instrumentation.md)|  
  
## <a name="related-sections"></a>Související oddíly  
 [Konfigurace výkonnostních relací](../profiling/configuring-performance-sessions.md)  
  
## <a name="see-also"></a>Viz také:  
 [Prohlížeč výkonu](../profiling/performance-explorer.md)