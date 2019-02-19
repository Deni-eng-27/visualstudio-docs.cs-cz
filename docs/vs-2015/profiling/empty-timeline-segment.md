---
title: Prázdný Segment časové osy | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.cv.threads.timeline.empty
helpviewer_keywords:
- Concurrency Visualizer, empty timeline segment
ms.assetid: f37b301f-3edc-4e56-8084-feec2dc5a9b1
caps.latest.revision: 16
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 4ac39a776cb7e6c2c9cbce648c0b3ca3ebc86783
ms.sourcegitcommit: a83c60bb00bf95e6bea037f0e1b9696c64deda3c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/19/2019
ms.locfileid: "54770742"
---
# <a name="empty-timeline-segment"></a>Prázdný segment časové osy
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Ve Vizualizátor souběžnosti, proč se části časové osy je prázdný (má bílé pozadí) závisí na typu vašeho kanálu.  
  
-   Pro kanál vlákna CPU znamená to, že vlákno neexistoval při tuto část časové osy. Pokud vás zajímá ve vlákně, najdete jeho provádění části pomocí ovládacího prvku přiblížení nebo posouvání vodorovně.  
  
-   Pro kanál vstupně-výstupních operací znamená to, že žádný přístup k disku došlo k jménem Cílový proces od tohoto okamžiku v čase.  
  
-   Pro kanál rozhraní DirectX znamená to, že se žádná práce GPU provedla jménem Cílový proces během této části časové osy.  
  
-   Pro značky kanál znamená to, že nevygenerovaly se žádné značky.  
  
## <a name="see-also"></a>Viz také  
 [Zobrazení vláken](../profiling/threads-view-parallel-performance.md)   
 [Ovládací prvek Lupa (Zobrazení vláken)](../profiling/zoom-control-threads-view.md)
