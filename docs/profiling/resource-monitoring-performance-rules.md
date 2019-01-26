---
title: Pravidla výkonu sledování prostředků | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: f0f77faf-0a05-4718-a2c5-47934be40868
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 352b4710f520d00eb97de5fd8c2b31be7e172c11
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54983115"
---
# <a name="resource-monitoring-performance-rules"></a>Pravidla výkonu sledování prostředků
Výkon zprávy v kategorii monitorování prostředků poskytují další data o výkonu vaší aplikace. Tato data můžete použít k analýze problémů výkonu. Tato pravidla jsou informační a nahlášených pro každé spuštění profilování.  
  
|||  
|-|-|  
|[DA0501: Průměrná spotřeba procesoru profilovaným procesem](../profiling/da0501-average-cpu-consumption-by-the-process-being-profiled.md)|Tato zpráva znamená procentuální hodnotu času, který byl procesor zaneprázdněný, provádění instrukcí z aplikace. Hlášená hodnota je průměrem přes všechny intervaly měření, ve kterých byl aktivní profilovaný proces.|  
|[DA0502: Maximální spotřeba procesoru profilovaným procesem](../profiling/da0502-maximum-cpu-consumption-by-the-process-being-profiled.md)|Tato zpráva znamená maximální procento času, který byl procesor zaneprázdněný, provádění instrukcí z aplikace. Hlášená hodnota je maximální hodnota uvedená mezi všechny intervaly měření, ve kterých byl aktivní profilovaný proces.|  
|[DA0503: Průměrná pracovní sada v bajtech profilovaného procesu](../profiling/da0503-average-working-set-in-bytes-for-the-process-being-profiled.md)|Tato zpráva hlásí Průměrná velikost fyzické paměti, v bajtech, které proces používal během profilace byl aktivní. Tato míra fyzické paměti se označuje jako pracovní sady.|  
|[DA0504: Maximální pracovní sada v bajtech profilovaného procesu](../profiling/da0504-maximum-working-set-in-bytes-for-the-process-being-profiled.md)|Tato zpráva znamená maximální velikost fyzické paměti, v bajtech, které proces používal během profilace byl aktivní.|  
|[DA0505: Průměrné nesdílené bajty přidělené profilovanému procesu](../profiling/da0505-average-private-bytes-allocated-for-the-process-being-profiled.md)|Tato zpráva hlásí Průměrná velikost virtuální paměti, že byl aktivní proces přidělených bajtů při profilování. Tato míra virtuální paměti se označuje jako *Nesdílené bajty*. Nesdílené bajty představuje virtuální paměti umístění, které byly přiděleny procesem, který je přístupný pouze tím, že běží uvnitř procesu vlákna.|  
|[DA0506: Maximální nesdílené bajty přidělené profilovanému procesu](../profiling/da0506-maximum-private-bytes-allocated-for-the-process-being-profiled.md)|Tato zpráva hlásí maximální velikost virtuální paměti, že byl aktivní proces nesdílených bajtů přidělených při profilování.|