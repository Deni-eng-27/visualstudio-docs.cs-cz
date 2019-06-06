---
title: Použití metod profilace z příkazového řádku k získání údajů o výkonu
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 5613fafc-f298-4e7a-9a2d-a853b61cdf9c
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 5b5f2c1d350f487b6490d0c2b4ce4fe0b83bb38f
ms.sourcegitcommit: 12f2851c8c9bd36a6ab00bf90a020c620b364076
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/06/2019
ms.locfileid: "66746769"
---
# <a name="use-profiling-methods-to-collect-performance-data-from-the-command-line"></a>Použití metod profilace ke shromažďování dat výkonu z příkazového řádku
Podle vaší volby [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] příkazového řádku nástrojů pro profilaci a možnosti závisí na faktorech jako typ aplikace, který profilujete, metodě profilování, který chcete použít, a určuje, zda je cílová aplikace napsané v nativní nebo .NET Kódu architektury.

 V tomto tématu jsou uspořádané příkazového řádku témat s postupy podle zvolené metodě profilování.

## <a name="use-the-sampling-method-to-collect-performance-statistics"></a>Shromažďování statistik výkonu pomocí metody vzorkování
 Metody nástroje pro profilaci vzorkování shromažďuje údaje o výkonu v pravidelných intervalech během spuštění profilování. Vzorkování dat může poskytnout přehled o problémy s výkonem vázané na procesor a může být dobrým způsobem, jak začít prozkoumávat výkon aplikace.

 Můžete spustit profiler a aplikace ve stejnou dobu, nebo můžete připojení profileru k běžící instance aplikace.

|Úloha|Typ cílové aplikace|
|----------|-----------------------------|
|**Spuštění aplikace**|-   [Samostatné aplikace](../profiling/how-to-launch-a-stand-alone-app-and-collect-application-statistics.md)|
|**Připojit ke spuštěnému procesu**|-   [Samostatné aplikace rozhraní .NET framework](../profiling/how-to-attach-the-profiler-to-a-dotnet-app-and-collect-application-statistics.md)<br />-   [Nativní samostatné aplikace](../profiling/how-to-attach-the-profiler-to-a-native-app-and-collect-application-statistics.md)<br />-   [Webové aplikace ASP.NET](../profiling/how-to-attach-the-profiler-to-an-aspnet-web-application-to-collect-application-statistics-by-using-the-command-line.md)<br />-   [Služby rozhraní .NET](../profiling/how-to-attach-the-profiler-to-a-dotnet-service-to-collect-application-statistics-by-using-the-command-line.md)<br />-   [Nativní služby](../profiling/how-to-attach-the-profiler-to-a-native-service-to-collect-application-statistics-by-using-the-command-line.md)|

## <a name="use-the-instrumentation-method-to-collect-detailed-timing-data"></a>Shromažďování podrobných dat časování pomocí metody instrumentace
 Metody nástroje pro profilaci instrumentace shromažďuje údaje o výkonu z kopie binární soubory aplikace, které obsahují software sondy, informace o záznamu výkonu. Na začátek a konec jednotlivých instrumentované funkcí a při každém volání dalších funkcí z instrumentované funkce se shromažďují data instrumentace. Metody instrumentace je užitečná při odhalování problémů s výkonem pomocí problémy vstupně-výstupních operací, jako je využití místa na disku.

 Vytvoření instrumentovaný binární soubor s [VInstr.exe](../profiling/vsinstr.md) nástroj. Po inicializaci profileru, data se automaticky shromažďují z instrumentované binární soubory při spuštění cílové aplikace.

 **Typ cílové aplikace**

- [Samostatné součásti rozhraní .NET framework](../profiling/how-to-instrument-a-dotnet-framework-component-and-collect-timing-data.md)

- [Nativní samostatné součásti](../profiling/how-to-instrument-a-native-component-and-collect-timing-data.md)

- [Staticky kompilované webové aplikace ASP.NET](../profiling/how-to-instrument-statically-compiled-aspnet-and-collect-detailed-timing-data.md)

- [Dynamicky kompilované webové aplikace ASP.NET](../profiling/how-to-instrument-a-dynamically-compiled-aspnet-app-and-collect-timing-data.md)

- [Služby rozhraní .NET](../profiling/how-to-instrument-a-dotnet-service-and-collect-detailed-timing-data-by-using-the-profiler-command-line.md)

- [Nativní služby](../profiling/how-to-instrument-a-native-service-and-collect-detailed-timing-data-by-using-the-profiler-command-line.md)

## <a name="use-net-memory-methods-to-collect-memory-allocation-and-object-lifetime-data"></a>Použijte metody paměti .NET ke shromažďování dat paměti přidělení a objekt životnosti
 Metoda paměti .NET nástrojů pro profilaci umožňuje shromažďovat data o přidělování paměti rozhraní .NET Framework a informace o životnosti objektů v rozhraní .NET Framework.

 Můžete spustit cílovou aplikaci pomocí profileru; můžete připojení profileru k běžící instance aplikace. a můžete vytvořit instrumentované verze této aplikace ke shromažďování podrobných informací o časování spolu s daty paměti rozhraní .NET Framework.

|Úloha|Typ cílové aplikace|
|----------|-----------------------------|
|**Spuštění aplikace**|-   [Samostatné aplikace rozhraní .NET Framework](../profiling/how-to-launch-a-stand-alone-dotnet-framework-app-to-collect-memory-data.md)|
|**Připojit ke spuštěnému procesu**|-   [Samostatné aplikace rozhraní .NET framework](../profiling/how-to-attach-the-profiler-to-a-dotnet-framework-app-to-collect-memory-data.md)<br />-   [Webové aplikace ASP.NET](../profiling/how-to-attach-the-profiler-to-an-aspnet-web-application-to-collect-memory-data-by-using-the-command-line.md)<br />-   [Služby rozhraní .NET](../profiling/how-to-attach-the-profiler-to-a-dotnet-service-to-collect-memory-data-by-using-the-command-line.md)|
|**Nástroj moduly**|-   [Samostatné součásti rozhraní .NET framework](../profiling/how-to-instrument-a-dotnet-framework-component-and-collect-memory-data.md)<br />-   [Staticky kompilované webové aplikace ASP.NET](../profiling/how-to-instrument-a-statically-compiled-aspnet-app-and-collect-memory-data.md)<br />-   [Dynamicky kompilované webové aplikace ASP.NET](../profiling/how-to-instrument-a-dynamically-compiled-aspnet-web-application-and-collect-memory-data.md)<br />-   [Služby rozhraní .NET](../profiling/how-to-instrument-a-dotnet-framework-service-and-collect-memory-data-by-using-the-profiler-command-line.md)|

## <a name="use-the-concurrency-method-to-collect-resource-contention-and-thread-activity-data"></a>Pomocí za použití metody souběžnosti můžete shromažďovat data aktivita prostředku kolize a vlákna
 Za použití metody souběžnosti nástrojů pro profilaci sady umožňuje shromažďovat kolize prostředků a dat aktivit vláken a procesů z aplikací s více vlákny.

 Aplikaci můžete spustit pomocí profileru, nebo můžete připojení profileru k běžící instance aplikace.

|Úloha|Typ cílové aplikace|
|----------|-----------------------------|
|**Spuštění aplikace**|-   [Samostatné aplikace rozhraní .NET Framework](../profiling/how-to-launch-a-stand-alone-dotnet-framework-app-to-collect-concurrency-data.md)<br />-   [Samostatné nativní aplikace](../profiling/how-to-launch-a-stand-alone-native-application-to-collect-concurrency-data.md)|
|**Připojit ke spuštěnému procesu**|-   [Samostatné aplikace rozhraní .NET framework](../profiling/how-to-attach-the-profiler-to-a-dotnet-app-and-collect-concurrency-data.md)<br />-   [Nativní samostatné aplikaci](../profiling/how-to-attach-the-profiler-to-a-native-app-and-collect-concurrency-data.md)<br />-   [Webová aplikace ASP.NET](../profiling/how-to-attach-the-profiler-to-an-aspnet-web-application-to-collect-concurrency-data-by-using-the-command-line.md)<br />-   [Služby rozhraní .NET](../profiling/how-to-attach-the-profiler-to-a-dotnet-service-to-collect-concurrency-data-by-using-the-command-line.md)<br />-   [Nativní služby](../profiling/how-to-attach-the-profiler-to-a-native-service-to-collect-concurrency-data-by-using-the-command-line.md)|

## <a name="add-tier-interaction-data-to-a-profiling-run"></a>Přidání dat interakce vrstvy do běhu profilování
 Přidání dat interakce vrstvy do běhu profilování vyžaduje zvláštní procedury s nástroji pro profilaci příkazového řádku. Zobrazit [shromažďování dat interakce vrstev](../profiling/adding-tier-interaction-data-from-the-command-line.md)

## <a name="see-also"></a>Viz také:
- [Samostatné aplikace profilu](../profiling/command-line-profiling-of-stand-alone-applications.md)
- [Webové aplikace ASP.NET profilu](../profiling/command-line-profiling-of-aspnet-web-applications.md)
- [Profil služby](../profiling/command-line-profiling-of-services.md)