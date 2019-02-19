---
title: Doba zpracování uživatelského rozhraní | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.cv.threads.timeline.uiprocessing
helpviewer_keywords:
- Concurrency Visualizer, UI Processing Time
ms.assetid: 0ddb05a3-8c6b-448b-8488-2751c1e5abcc
caps.latest.revision: 10
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 4bbed9d8c4725b6bd497377d4a9dee22f2f8573d
ms.sourcegitcommit: a83c60bb00bf95e6bea037f0e1b9696c64deda3c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/19/2019
ms.locfileid: "54783441"
---
# <a name="ui-processing-time"></a>Doba zpracování uživatelského rozhraní
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Tyto segmenty na časové ose jsou přidruženy k blokování časy, které jsou klasifikovány jako zpracování uživatelského rozhraní. Z toho vyplývá, že vlákno – čerpání zpráv Windows nebo provádění jiné práce uživatelské rozhraní (UI). Během této doby je zablokovaný vlákno v rozhraní API, které Vizualizátor souběžnosti se počítá jako zpracování uživatelského rozhraní. Rozhraní API, jako `GetMessage()` a `MsgWaitForMultipleObjects()` spadají do této skupiny.  
  
 Pokud se zjistí, žádné předdefinované blokování rozhraní API, projděte si zásobníky volání a profilu, sestavy určit základní příčiny zpoždění.  
  
 Kategorie zpracování uživatelského rozhraní je důležité pochopit, rychlost odezvy aplikací grafického uživatelského rozhraní a je žádoucí v aplikacích, které závisí na rychlosti odezvy uživatelského rozhraní. Například pokud vlákno uživatelského rozhraní v aplikaci dosáhne 100 % času v zpracování uživatelského rozhraní, je pravděpodobně velmi rychlou odezvou. Pokud vlákno uživatelského rozhraní stráví značnou dobu v jiných kategoriích, ale hledat hlavní příčiny a zvažte možnosti snížení kategorie bez uživatelského rozhraní v daném vláknu.  
  
## <a name="see-also"></a>Viz také  
 [Zobrazení vláken](../profiling/threads-view-parallel-performance.md)
