---
title: "Referenční dokumentace pravidel výkonu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 59fc9424-76ca-4365-ae47-bb14a736c9c2
caps.latest.revision: "14"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: bec05a24a932816374766c107c1aab6f018e77cf
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="performance-rules-reference"></a>Referenční dokumentace pravidel výkonu
Pravidel výkonu nástrojů pro profilaci poskytují další upozornění a informace o výkonu vaší aplikace. Pravidla výkonu analyzovat data v profilaci spuštění, které se shromažďují ze zdroje, například Windows a čítače výkonu procesoru. Pravidlo zprávy se zobrazují v okně výstupu chyba [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] integrované vývojové prostředí. Zprávy jsou uvedeny s jedním z následujících úrovní pravidlo:  
  
|||  
|-|-|  
|**Chyba**|Několik pravidel vygenerovat chybové zprávy, protože většina problémy s výkonem nejsou přímý chyby. Chybová zpráva může označují selhání shromažďovat data profilování.|  
|**Upozornění**|Upozornění označují oblast vaší aplikace, která potenciálně může být zdrojem problémy s výkonem nebo který může mít užitek z optimalizace.|  
|**Informace o**|Zprávy s informacemi o označuje, že buď analýzu podmínku pravidla nebylo dosaženo prahové hodnoty pro generování chybovou zprávu, nebo že je užitečné informace ve zprávě, ale nemusí odpovídat problémy s výkonem.|  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Pravidla výkonu podle identifikátorů](../profiling/performance-rules-by-id.md)  
  
 Pravidla výkonu nástrojích pro profilaci jsou uspořádány do čtyř kategorií:  
  
|||  
|-|-|  
|[Pravidla výkonu použití rozhraní .NET framework](../profiling/dotnet-framework-usage-performance-rules.md)|Pravidla, které vám pomůžou efektivně používat rozhraní .NET Framework.|  
|[Paměti a stránkování pravidla výkonu](../profiling/memory-and-paging-performance-rules.md)|Pravidla, která analýza spravované paměti a stránkování chování vaší aplikace.|  
|[Pravidla používání nástrojů pro profilaci](../profiling/profiling-tools-usage-rules.md)|Pravidla, které vám pomůžou nástrojích pro profilaci efektivně používat.|  
|[Pravidla výkonu sledování prostředků](../profiling/resource-monitoring-performance-rules.md)|Informační zprávy o využití procesoru a paměti v profilaci spustit.|