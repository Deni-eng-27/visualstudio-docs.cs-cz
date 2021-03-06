---
title: Používání více nástrojů profileru současně | Microsoft Docs
ms.date: 4/29/2020
ms.topic: how-to
helpviewer_keywords:
- Profiler, multiple tools
author: Sagar-S-S
ms.author: sashe
manager: AndSter
ms.workload:
- multiple
ms.openlocfilehash: f72757d46496c3990c0a0d4205753d185078eac7
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "85332032"
---
# <a name="using-multiple-profiler-tools-simultaneously"></a>Souběžné používání více nástrojů profileru

Profiler výkonu byl navržený tak, aby bylo možné použít ve stejné relaci více nástrojů, které pomáhají pochopit problémy s výkonem. Většina nástrojů v profileru výkonu podporuje současné spuštění, jako je [využití CPU](../profiling/cpu-usage.md), [asynchronní nástroj .NET](../profiling/analyze-async.md)a [databázový](../profiling/analyze-database.md) nástroj. Pokud chcete spouštět nástroje současně ve stejné diagnostické relaci, zaškrtněte políčko vedle sebe a spusťte diagnostickou relaci.

![Diagnostika všech vybraných nástrojů v centrálním centru](../profiling/media/diaghuballtoolsselected.png "Diagnostika všech vybraných nástrojů v centrálním centru")

>[!NOTE]
>Některé nástroje, jako je například nástroj pro [přidělování objektů rozhraní .NET](../profiling/dotnet-alloc-tool.md) , nelze spustit s jinými nástroji z důvodu jejich vysoké režie nebo z důvodu jiných technických omezení.

## <a name="time-filtering"></a>Filtrování času 

Během analýzy se operace filtrování času používají napříč nástroji, takže můžete použít informace v jednom nástroji k zúžení časového rozsahu a filtrování dat v jiném nástroji. Tato funkce pomáhá analyzovat v průvodci konkrétní body v trasování a pomáhá pochopit stav aplikace.

![Filtrování času diagnostiky centra](../profiling/media/diaghubtimefiltering.png "Filtrování času diagnostiky centra")

## <a name="see-also"></a>Viz také

- [Optimalizace nastavení profileru](../profiling/optimize-profiler-settings.md)
- [Spuštění nástrojů pro profilaci s ladicím programem nebo bez něj](../profiling/running-profiling-tools-with-or-without-the-debugger.md)
- [Porozumění metodám shromažďování údajů o výkonu](../profiling/understanding-performance-collection-methods-perf-profiler.md)
