---
title: 'DA0013: Vysoké použití String.Split nebo String.Substring | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.13
- vs.performance.rules.DAAvoidStringSubstr
- vs.performance.DA0013
- vs.performance.rules.DA0013
helpviewer_keywords:
- vs.performance.13
- vs.performance.rules.DA0013
ms.assetid: f501f423-bef9-4e08-bf96-c9ac9957e5a2
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c218dd9a7ee3266de2cf9e07933ed69aa23e73e7
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/04/2018
ms.locfileid: "34749879"
---
# <a name="da0013-high-usage-of-stringsplit-or-stringsubstring"></a>DA0013: Vysoké použití String.Split nebo String.Substring
|||  
|-|-|  
|Id pravidla|DA0013|  
|Kategorie|Pokyny pro používání rozhraní .NET framework|  
|Metod profilace|Vzorkování|  
|Zpráva|Zvažte snížení použití String.Split a String.Substring funkce.|  
|Typ pravidla|Upozornění|  
  
## <a name="cause"></a>příčina  
 Volání metody System.String.Split nebo System.String.Substring jsou podstatnou část data profilování. Zvažte použití System.String.IndexOf nebo System.String.IndexOfAny Pokud testujete existenci substring v řetězci.  
  
## <a name="rule-description"></a>Popis pravidla  
 Metoda rozdělení funguje na objekt řetězce a vrátí nové pole řetězců obsahující dílčích řetězců původního. Funkce přidělí paměť pro objekt vrácený pole a přiděluje nový objekt řetězce pro každý element pole, které najde. Substr – metoda podobně pracuje na objekt řetězce a vrátí nové řetězec, který je ekvivalentní požadovaný dílčí řetězec.  
  
 Pokud Správa přidělení paměti je rozhodující ve vaší aplikaci, zvažte použití alternativních metod String.Split a String.Substr. Například můžete použít metodu IndexOf nebo IndexOfAny najít konkrétní podřetězce v rámci znak řetězec bez vytvoření nové instance třídy String.  
  
## <a name="how-to-investigate-a-warning"></a>Jak prozkoumat upozornění  
 Dvakrát klikněte na zprávu ve **seznam chyb** přejděte do okna [zobrazení podrobností funkce](../profiling/function-details-view.md) odběru data profilu. Zkontrolujte volání funkcí najít v částech programu, které využívají nejčastěji se vyskytující metod System.String.Split nebo System.String.Substr. Pokud je to možné použijte metodu IndexOf nebo IndexOfAny najít konkrétní podřetězce v rámci znak řetězec bez vytvoření nové instance třídy String.