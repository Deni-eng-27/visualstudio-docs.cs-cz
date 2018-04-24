---
title: Zobrazení stromu volání | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.view.calltree
helpviewer_keywords:
- Call Tree view
- profiling tools reports, Call Tree view
- performance reports, Call Tree view
- profiling tools, Call Tree view
ms.assetid: b2dbc033-bf95-4d10-8e51-f9462979133e
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4f098b18100bd54e8078ea0c855a1b3e51926b93
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="call-tree-view"></a>Zobrazení stromu volání
Zobrazení stromu volání zobrazuje cesty provádění funkce, které byly provázán v PROFILOVANÉHO aplikaci. Kořen stromu je vstupním bodem do součást nebo aplikace. Každý uzel funkce uvádí všechny funkce, které ji volat a údaje o výkonu o těchto volání funkcí.  
  
 Zobrazení stromu volání můžete také rozšířit a zvýraznit cestu spuštění funkce, která nejvíce času spotřebovaného nebo byl vzorkovat nejčastěji. Zobrazení výkonu nejnákladnější cesty, klikněte pravým tlačítkem na funkci a pak klikněte na **rozbalte aktivní trase**.  
  
 Každý proces v profilaci spuštění se zobrazí jako kořenový uzel. Počáteční uzel zobrazení stromu volání můžete nastavit tak, že kliknete pravým tlačítkem na uzel, který chcete nastavit jako počáteční uzel a potom vyberete **nastavit kořenové**.  
  
 Pokud nastavíte kořenového uzlu, můžete eliminovat všechny položky ze zobrazení s výjimkou podstrom vybraného uzlu. Zpět do uzlu prohlížené můžete resetovat kořenového uzlu. V okně zobrazení stromu volání, klikněte pravým tlačítkem a pak vyberte **resetovat kořenové**.  
  
 Zobrazení stromu volání můžete přizpůsobit tak, aby přidat nebo odebrat sloupce. Klikněte pravým tlačítkem myši **záhlaví sloupce názvem**a potom vyberte **přidat nebo odebrat sloupce**.  
  
 Zobrazení stromu volání mohou být konfigurovány pro snížení šumu omezením množství dat, který se zobrazí. Pomocí snížení šumu jsou problémy s výkonem výraznější v zobrazení. Pokud jsou snadno rozlišit problémy s výkonem, analýza je snazší. Další informace najdete v tématu [postupy: Konfigurace snížení šumu v zobrazeních sestav](../profiling/how-to-configure-noise-reduction-in-report-views.md).  
  
> [!NOTE]
>  Pokud snížení šumu nastaven tak, aby zobrazila upozornění, pokud je povolena, zobrazí se v sestavě zobrazí informační panel.  
  
 Další informace o definicích pro sloupce v zobrazení stromu volání naleznete v následujících tématech:  
  
 [Zobrazení stromu volání](../profiling/call-tree-view-sampling-data.md)  
  
 [Zobrazení stromu volání](../profiling/call-tree-view-instrumentation-data.md)  
  
 [Zobrazení stromu volání – vzorkování](../profiling/call-tree-view-dotnet-memory-sampling-data.md)  
  
 [Zobrazení stromu volání](../profiling/call-tree-view-contention-data.md)  
  
## <a name="see-also"></a>Viz také  
 [Zobrazení sestav výkonu](../profiling/performance-report-views.md)   
 [Porozumění hodnotám dat instrumentace](../profiling/understanding-instrumentation-data-values.md)   
 [Porozumění hodnotám dat vzorkování](../profiling/understanding-sampling-data-values.md)