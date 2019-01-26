---
title: Pravidla používání nástrojů pro profilaci | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: afa7db3b-8c1d-473a-81ac-24ede112a17f
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 67d9d98ed089c8afc32cc8daba2ca029ccd99101
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54987437"
---
# <a name="profiling-tools-usage-rules"></a>Pravidla používání nástrojů pro profilaci
Pravidla výkonu v kategorii použití nástroje pro profilaci poskytují pokyny k používání profiler k co nejefektivnějšímu shromažďovat data.  


| | |
| - | - |
| [DA0002: Chybí knihovna VSPerfCorProf.dll](../profiling/da0002-vsperfcorprof-dll-is-missing.md) | Profilace příkazový řádek může obsahovat neúplná data pro [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] binární soubory. Příčinou může není nastavení proměnných správné prostředí. |
| [DA0003: Velký počet ukázek jádra](../profiling/da0003-many-kernel-samples.md) | Mnoho profilace vzorků, ke kterým došlo mimo provádění cílový binární soubor byly zaznamenány. Pokud chcete přesnější data shromažďovat, zvažte použití metody instrumentace. |
| [DA0004: Vysoké využití procesoru](../profiling/da0004-high-processor-usage.md) | Data profilování naznačuje, že byly vaše procesory konzistentně zaneprázdněný během spuštění profilování. Pokud chcete přesnější data shromažďovat, zvažte použití metody vzorkování. |
| [DA0008: Shromážděno málo vzorků](../profiling/da0008-few-samples-collected.md) | Počet vzorků shromážděné při spuštění profilace nebyla dostatečně vysoká, aby se statisticky významná. Zvažte profilaci znovu a spuštění aplikace delší dobu. Pomocí metody instrumentace ke shromažďování dat můžete také zvážit. |
| [DA0026: Nadměrný čas zpracování procesoru jádra](../profiling/da0026-excessive-kernel-cpu-time-processing.md) | V režimu jádra procesoru došlo k významné množství času během spuštění profilování. Vezměte v úvahu vzorkování pomocí systémových volání jako metriku namísto používání času jako metriku. |
| [DA0029: Nepodporovaná verze CLR](../profiling/da0029-unsupported-clr-version.md) | PROFILOVANÉHO binární soubor používá verzi [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] pomocí profileru, který není podporován. Sestavy profileru nelze přeložit názvy symbolů. |
| [DA0030: Získání měření interakce vrstev pro databázové projekty](../profiling/da0030-gather-tier-interaction-measurements-for-database-projects.md) | Velký počet volání metod v <xref:System.Data?displayProperty=fullName> shromáždilo se obor názvů. Chcete-li obsahují data o volání databáze, zvažte, spustí shromažďování dat interakce vrstev ve vašem profilu. |
