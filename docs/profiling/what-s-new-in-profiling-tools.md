---
title: "Co je nového v profilaci | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- profiling
- what's new
ms.assetid: d4736cc8-8961-4089-be9e-d5190ce8353c
caps.latest.revision: "42"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 8529bc4cc9708ea58a0480d61327c50c96c996fc
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="whats-new-in-profiling-tools-in-includevsdev15miscincludesvsdev15mdmd"></a>Co je nového v nástrojích pro profilaci v[!include[vs_dev15](../misc/includes/vs_dev15_md.md)]
Nástroje pro diagnostiku zahrnují nové vizualizace můžete identifikovat problémy ve vaší aplikaci, potřebujete opravit. Diagnostické nástroje nyní zahrnují podporu pro aplikace ASP.NET.

Další informace najdete v tématu [poznámky k verzi pro [!include[vs_dev15](../misc/includes/vs_dev15_md.md)] ](https://www.visualstudio.com/en-us/news/releasenotes/vs2017-relnotes#debuggingdiag).

A **Souhrn** přidala karta nástroje, které vám pomůže se zaměřit na klíčové oblasti pro analýzy výkonu. Na této kartě ukazuje, kolik události došlo, umožňuje pořízení snímků halda a umožňuje rychle Povolit shromažďování dat o využití procesoru. Toto zobrazení uvádí všechny [Application Insights](https://azure.microsoft.com/en-us/documentation/articles/app-insights-visual-studio/) nebo [uživatelského rozhraní Analysis](https://www.visualstudio.com/en-us/news/releasenotes/vs2017-relnotes#UIAnalysis) události. Pro Visual Studio Enterprise, je kromě toho toto zobrazení také uvádí události IntelliTrace.

![Diagnostické nástroje kartu Souhrn](../profiling/media/DiagToolsSummaryTab-2.png "DiagToolsSummaryTab")

Má nástroj využití procesoru [nové vizualizace](../profiling/Beginners-Guide-to-Performance-Profiling.md) usnadňující identifikaci funkce, které se nejpravděpodobněji způsobovat problémy s výkonem. Nové **volající/volaný** zobrazení umožňuje prozkoumat náklady funkce volání provedená do a z vybrané funkce.

![Diagnostické nástroje volající volaný – zobrazení](../profiling/media/DiagToolsCallerCallee.png "DiagToolsCallerCallee")
  
## <a name="see-also"></a>Viz také  
 [Profilace v sadě Visual Studio](../profiling/index.md)  
 [Prohlídka funkce profilace](../profiling/profiling-feature-tour.md)