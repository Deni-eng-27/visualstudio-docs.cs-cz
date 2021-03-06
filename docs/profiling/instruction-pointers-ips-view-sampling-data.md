---
title: Zobrazení ukazatelů na instrukce (IP) – vzorkování dat | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Instruction Pointers view
ms.assetid: c7f647bb-c5a3-4708-9f9d-33c0fd6e2e96
author: mikejo5000
ms.author: mikejo
manager: jillfra
monikerRange: vs-2017
ms.workload:
- multiple
ms.openlocfilehash: 42398e044bfc06e41249b15ac9baeebcaebd19f6
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "74774253"
---
# <a name="instruction-pointers-ips-view---sampling-data"></a>Zobrazení ukazatelů na instrukce (IP) – vzorkování dat
Zobrazení IP adres dat vzorkování obsahuje údaje o výkonu pro pokyny k sestavení, které byly přímo spouštěny, když byly vzorky shromážděny při spuštění profilace.

> [!NOTE]
> Rozšířené funkce zabezpečení ve Windows 8 a Windows Serveru 2012 vyžadují významné změny ve způsobu, jakým Profiler sady Visual Studio shromažďuje data na těchto platformách. Aplikace pro UWP také vyžadují nové techniky shromažďování. Podívejte [se na nástroje pro sledování výkonu v aplikacích pro Windows 8 a Windows Server 2012](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).

|Sloupec|Popis|
|------------|-----------------|
|**ID procesu**|ID procesu (PID) pro spuštění profilace.|
|**Název procesu**|Název procesu|
|**Název modulu**|Název modulu, který obsahuje instrukci.|
|**Cesta k modulu**|Cesta modulu, který obsahuje instrukci.|
|**Zdrojový soubor**|Zdrojový soubor, který obsahuje instrukci.|
|**Název funkce**|Název funkce, která obsahuje instrukci.|
|**Číslo řádku funkce**|Číslo řádku začátku této funkce ve zdrojovém souboru.|
|**Adresa funkce**|Počáteční adresa paměti funkce v načteném binárním souboru.|
|**Začátek řádku zdroje**|Číslo počátečního řádku ve zdrojovém souboru, ve kterém byl tento vzorek shromážděn.|
|**Konec řádku zdroje**|Číslo koncového řádku ve zdrojovém souboru, ve kterém byl tento vzorový vzorek shromážděn.|
|**Začátek zdrojového znaku**|Posun počátečního znaku v řádku zdrojového souboru, na kterém byla tato ukázka shromážděna.|
|**Konec zdrojového znaku**|Posun koncového znaku na řádku zdrojového souboru, na kterém byla tato ukázka shromážděna.|
|**Adresa instrukce**|Adresa instrukcí v načteném binárním souboru.|
|**Exkluzivní vzorky**|Celkový počet vzorků, které byly shromážděny při provádění instrukcí.|
|**% Exkluzivních vzorků**|Procentuální podíl všech vzorků v běhu profilace, které byly shromážděny při provádění instrukce.|

## <a name="see-also"></a>Viz také
- [Zobrazení ukazatelů na instrukce (IP) – vzorkování](../profiling/instruction-pointers-ips-view-dotnet-memory-sampling-data.md)
