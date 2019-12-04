---
title: 'DA0021: vysoká míra pro uvolňování paměti 1. generace | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.performance.21
- vs.performance.DA0021
- vs.performance.rules.DA0021
ms.assetid: ebf5d9b3-a1ac-4688-8f0f-39a85f4dd15f
author: mikejo5000
ms.author: mikejo
manager: jillfra
monikerRange: vs-2017
ms.workload:
- multiple
ms.openlocfilehash: 36350b59a3d70f8553fddc5f58bf5c79716fa3aa
ms.sourcegitcommit: 00b71889bd72b6a566586885bdb982cfe807cf54
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/03/2019
ms.locfileid: "74777657"
---
# <a name="da0021-high-rate-of-gen-1-garbage-collections"></a>DA0021: Vysoká míra 1. generace uvolňování pamětí

|||
|-|-|
|Id pravidla|DA0021|
|Kategorie|Využití .NET Framework|
|Metody profilace|Vše|
|Zpráva|Dochází k poměrně vysoké míře pro uvolňování paměti 1. generace. Pokud je podle návrhu většina datových struktur programu přidělená a trvalá po dlouhou dobu, není to obvykle problém. Nicméně, pokud je toto chování nezamýšlené, vaše aplikace může Připnutí objektů. Pokud si nejste jistí, můžete shromáždit údaje o přidělení paměti .NET a informace o životnosti objektů, abyste pochopili, jaký model přidělení paměti vaše aplikace používá.|
|Typ pravidla|Informace o nástroji|

 Když použijete profilování pomocí vzorkování, paměti .NET nebo způsobů kolizí prostředků, musíte pro aktivaci tohoto pravidla shromáždit aspoň 10 vzorků.

## <a name="cause"></a>příčina
 Údaje o výkonu systému, které byly shromážděny během profilace, naznačují, že významný podíl objektů paměti for.NET Framework byl získán v generaci 1 uvolňování paměti v porovnání s kolekcí dat generace 0.

## <a name="rule-description"></a>Popis pravidla
 Modul CLR (Common Language Runtime) platformy Microsoft .NET poskytuje automatický mechanismus správy paměti, který používá systém uvolňování paměti k uvolnění paměti z objektů, které aplikace již nepoužívá. Systém uvolňování paměti je zaměřený na generaci, a to na základě předpokladu, že mnoho přidělení je krátkodobé. Místní proměnné, například by měly být krátkodobé. Nově vytvořené objekty začínají v generaci 0 (gen 0) a poté budou dokončeny na generaci 1, když přestanou běžet v uvolňování paměti, a nakonec přechod na generaci 2, pokud je aplikace stále používá.

 Objekty v generaci 0 jsou často shromažďovány a obvykle velmi efektivně. Objekty v generaci 1 jsou shromažďovány méně často a méně efektivní. A konečně dlouhodobé objekty v generaci 2 by měly být shromažďovány ještě méně často. Největší náročná operace je shromažďování 2, což je úplné spuštění uvolňování paměti.

 Toto pravidlo je vyvoláno, když došlo k poměru příliš velkého počtu uvolňování paměti generace 1. Pokud příliš mnoho poměrně krátkodobých objektů předrželo kolekci 0 generace, ale je možné je shromáždit v kolekci 1. generace, náklady na správu paměti mohou být nadměrné. Další informace najdete v části věnované [krizi v polovině životního cyklu](https://blogs.msdn.microsoft.com/ricom/2003/12/04/mid-life-crisis/) na webu MSDN na Mariani výkonu pikantní.

## <a name="how-to-investigate-a-warning"></a>Jak prozkoumat upozornění
 Dvakrát klikněte na zprávu v okně Seznam chyb, abyste přešli na [zobrazení značek](../profiling/marks-view.md) dat profilování. Vyhledá **paměť .NET clr\\# z kolekcí gen 0** a **paměti .NET CLR\\počet sloupců kolekcí 1. generace** . Určete, zda jsou k dispozici určité fáze provádění programu, kde dochází k uvolňování paměti často. Porovnejte tyto hodnoty se sloupcem **% času ve uvolňování** paměti, abyste viděli, jestli se při přidělení spravované paměti nejedná o nadměrné nároky na správu paměti.

 Chcete-li pochopit vzor využití spravované paměti aplikací, profil znovu spusťte profil přidělení paměti a.NET a vyžádejte si měření životnosti objektu.

 Informace o tom, jak zlepšit výkon uvolňování paměti, najdete v tématu [základy systému uvolňování paměti a Nápověda ke zvýšení výkonu](/previous-versions/dotnet/articles/ms973837(v=msdn.10)) na webu společnosti Microsoft. Informace o režii automatického uvolňování paměti najdete v tématu [large object halda se nepokryla](https://msdn.microsoft.com/magazine/cc534993.aspx).
