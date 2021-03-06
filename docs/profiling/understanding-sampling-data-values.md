---
title: Porozumění hodnotám dat vzorkování | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- sampling profiling method
- Profiling Tools, sampling
author: mikejo5000
ms.author: mikejo
manager: jillfra
monikerRange: vs-2017
ms.workload:
- multiple
ms.openlocfilehash: 289f92deaceca32a44249ed77c17187743a34fa4
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "74778047"
---
# <a name="understand-sampling-data-values"></a>Porozumění hodnotám dat vzorkování

Metoda profilování *vzorkování* sady Visual Studio nástroje pro profilaci přerušuje procesor počítače v nastavených intervalech a shromáždí zásobník volání funkce. *Zásobník volání* je dynamická struktura, která ukládá informace o funkcích, které jsou spuštěny na procesoru.

Analýza profileru určuje, zda procesor spouští kód v cílovém procesu. Pokud procesor neprovádí kód v cílovém procesu, je ukázka zahozena.

Pokud procesor provádí cílový kód, Profiler zvýší počty vzorků pro každou funkci v zásobníku volání. V době, kdy je provedena ukázka, je aktuálně spuštěna pouze jedna funkce v zásobníku volání. Ostatní funkce v zásobníku jsou rodiče v hierarchii volání funkcí, které čekají na vrácení jejich podřízených objektů.

V případě ukázkové události Profiler zvýší počet *exkluzivních* vzorků funkce, ve které aktuálně probíhá zpracování instrukcí. Vzhledem k tomu, že exkluzivní vzorek je také součástí celkových (*včetně*) vzorků funkce, je také zvýšen celkový počet vzorků aktuálně aktivní funkce.

 Profiler zvýší celkový počet vzorků všech ostatních funkcí v zásobníku volání.

## <a name="inclusive-samples"></a>Vzorky včetně

Celkový počet vzorků, které jsou shromažďovány během provádění cílové funkce.

To zahrnuje ukázky, které jsou shromažďovány během přímého provádění kódu funkce a ukázky, které jsou shromažďovány během provádění podřízených funkcí, které jsou volány cílovou funkcí.

## <a name="exclusive-samples"></a>Exkluzivní vzorky

Počet vzorků, které jsou shromážděny při přímém provádění instrukcí cílové funkce.

Exkluzivní vzorky nezahrnují vzorky, které jsou shromažďovány během spouštění funkcí, které jsou volány cílovou funkcí.

## <a name="inclusive-percent"></a>Celkové procento

Procentuální podíl celkového počtu zahrnutých vzorků v průběhu profilace, včetně vzorků funkcí nebo rozsahu dat.

## <a name="exclusive-percent"></a>Exkluzivní procento

Procentuální podíl celkového počtu exkluzivních vzorků v průběhu profilace, které jsou exkluzivními ukázkami funkce nebo rozsahu dat.

## <a name="see-also"></a>Viz také

[Postupy: výběr metod shromažďování](../profiling/how-to-choose-collection-methods.md) 
 [Analýza dat nástrojů výkonu](../profiling/analyzing-performance-tools-data.md)
