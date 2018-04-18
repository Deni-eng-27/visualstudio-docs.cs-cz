---
title: Zobrazení funkcí – Data vzorkování paměti .NET | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- Functions view
ms.assetid: 5d9c6302-2ffd-430e-9535-13ce795f9f7c
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 1e3ee9fa3b927d05de9c08e913d5c8f96ead59db
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="functions-view---net-memory-sampling-data"></a>Zobrazení funkcí – Data vzorkování paměti .NET
Zobrazení funkcí přidělení paměti .NET profilace data, která nebyla shromážděna pomocí metody vzorkování uvádí funkce, které přidělené paměti při spuštění profilování a sestav velikost a počet přidělení.  
  
|Sloupec|Popis|  
|------------|-----------------|  
|**ID procesu**|ID procesu (PID) z profilace spustit.|  
|**Název procesu**|Název procesu.|  
|**Název modulu**|Název modulu, který obsahuje funkci.|  
|**Cesta modulu**|Cesta modul, který obsahuje funkce.|  
|**Zdrojový soubor**|Zdrojový soubor, který obsahuje definici pro tuto funkci.|  
|**Název funkce**|Plně kvalifikovaný název funkce.|  
|**Číslo řádku – funkce**|Číslo řádku spuštění této funkce ve zdrojovém souboru.|  
|**Adresa funkce**|Adresa funkce.|  
|**Přidělení (včetně).**|Celkový počet objektů, které byly přiděleny v tato funkce a jeho podřízené funkce.|  
|**% Přidělení (včetně).**|Procento všech objektů, které byly přiděleny v profilaci spuštění, které byly včetně přidělení této funkce.|  
|**Výhradní přidělení**|Počet objektů, které byly vytvořeny při provádění funkce přímo v horní části zásobníku volání. Toto číslo nezahrnuje objekty, které byly vytvořeny v podřízené funkce.|  
|**Výhradní přidělení %**|Procento všech objektů, které byly přiděleny v profilaci spuštění, které byly výhradní přidělení této funkce.|  
|**Bajtů (včetně).**|Počet bajtů paměti, které byly přiděleny tak, že tato funkce a jeho podřízené funkce.|  
|**% Bajtů (včetně).**|Procento všech bajtů paměti, které byly přiděleny v profilaci spuštění, které byly včetně bajtů této funkce.|  
|**Výhradní bajtů**|Počet bajtů paměti, které byly přiděleny tuto funkci, ale ne jeho podřízené funkce.|  
|**% Výhradní bajtů**|Procento všech bajtů paměti, které byly přiděleny v profilaci spuštění, které byly výhradní bajtů této funkce.|  
  
## <a name="see-also"></a>Viz také  
 [Zobrazení funkcí – instrumentace](../profiling/functions-view-dotnet-memory-instrumentation-data.md)   
 [Zobrazení funkcí](../profiling/functions-view-sampling-data.md)   
 [Zobrazení funkcí](../profiling/functions-view-instrumentation-data.md)