---
title: Shromažďování statistik aplikace pro samostatné aplikace pomocí příkazového řádku profileru | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- sampling profiling method
- profilng tools,sampling method
ms.assetid: be2dbdd0-fc88-45f9-a1d5-bcb4f64e17ad
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 69c9fe7ac91b8e4015204ee157f30c65583dc1df
ms.sourcegitcommit: 046a9adc5fa6d6d05157204f5fd1a291d89760b7
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/11/2018
---
# <a name="collecting-application-statistics-for-stand-alone-applications-by-using-the-profiler-command-line"></a>Shromažďování statistik aplikace pro samostatné aplikace pomocí příkazového řádku profileru
Tato část popisuje postupy a možnosti pro shromažďování statistik výkonu pro klientskou aplikaci (samostatná) pomocí metody vzorkování z příkazového řádku.  
  
> [!NOTE]
>  Funkce Rozšířené zabezpečení v systému Windows 8 a Windows Server 2012 vyžaduje významné změny ve způsobu, jakým Visual Studio profiler shromažďuje data na těchto platformách. Aplikace UWP také vyžadují nové techniky kolekce. V tématu [nástroje pro sledování výkonu v aplikacích pro Windows 8 a Windows Server 2012](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
  
## <a name="common-tasks"></a>Obecné úlohy  
  
|Úloha|Související obsah|  
|----------|---------------------|  
|**Spusťte aplikaci pomocí profilace**|-   [Postupy: spuštění samostatné aplikace a shromažďování statistik aplikace](../profiling/how-to-launch-a-stand-alone-application-with-the-profiler-and-collect-application-statistics-by-using-the-command-line.md)|  
|**Připojení profileru k spuštěné aplikace rozhraní .NET Framework**|-   [Postupy: připojení profileru k aplikaci .NET Framework a shromažďování statistik aplikace](../profiling/how-to-attach-the-profiler-to-a-dotnet-app-and-collect-application-statistics.md)|  
|**Připojení profileru k spuštěné aplikace C/C++**|-   [Postupy: připojení profileru k nativní aplikaci a shromažďování statistik aplikace](../profiling/how-to-attach-the-profiler-to-a-native-stand-alone-application-and-collect-application-statistics-by-using-the-command-line.md)|  
|**Přidání dat interakce vrstvy**|-   [Shromažďování dat interakce vrstev](../profiling/adding-tier-interaction-data-from-the-command-line.md)|  
  
## <a name="related-tasks"></a>Související úlohy  
  
### <a name="profiling-stand-alone-applications"></a>Profilace samostatných aplikací  
  
|Úloha|Související obsah|  
|----------|---------------------|  
|**Instrumentace aplikace**|-   [Shromažďování podrobných dat časování pomocí instrumentace](../profiling/collecting-detailed-timing-data-for-a-stand-alone-application.md)|  
|**Shromažďování .NET přidělení a uvolňování paměti shromažďování dat paměti**|-   [Shromažďování dat paměti .NET Framework](../profiling/collecting-dotnet-framework-memory-data-for-stand-alone-applications.md)|  
|**Shromažďování dat provádění prostředku kolizí a přístup z více vláken**|-   [Shromažďování dat souběžnosti](../profiling/collecting-concurrency-data-for-stand-alone-applications.md)|  
  
### <a name="profiling-by-using-the-sampling-method"></a>Profilace pomocí metody vzorkování  
  
|Úloha|Související obsah|  
|----------|---------------------|  
|**Profil webových aplikací ASP.NET**|-   [Shromažďování statistik aplikace pomocí vzorkování](../profiling/collecting-application-statistics-for-aspnet-using-the-profiler-sampling-method.md)|  
|**Profil služby**|-   [Shromažďování statistik aplikace pomocí vzorkování](../profiling/collecting-application-statistics-for-services-by-using-the-profiler-sampling-method.md). Popisuje, jak ke shromažďování statistik výkonu ze služeb systému Windows pomocí metody vzorkování.|  
  
### <a name="analyzing-sampling-data-views-and-reports"></a>Analýza dat vzorkování zobrazeních a sestavách  
 [Zobrazení dat metody vzorkování](../profiling/profiler-sampling-method-data-views.md)