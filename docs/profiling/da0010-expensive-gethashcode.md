---
title: 'DA0010: Náročná metoda GetHashCode | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.rules.DAExpensiveGetHashCode
- vs.performance.DA0010
- vs.performance.rules.DA0010
- vs.performance.10
ms.assetid: 3987e21a-5b4f-45e4-8a33-6b3f0a472c08
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d62976c7cf4d42dade449bc7fc97d79715f276be
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="da0010-expensive-gethashcode"></a>DA0010: Náročná metoda GetHashCode
|||  
|-|-|  
|Id pravidla|DA0010|  
|Kategorie|Použití rozhraní .NET framework|  
|Metod profilace|Vzorkování<br /><br /> Využívání paměti rozhraním .NET|  
|Zpráva|Funkce GetHashCode by měl být levných a není přidělit paměť. Pokud je to možné snížit složitost kódu funkce hash.|  
|Typ zprávy|Upozornění|  
  
## <a name="cause"></a>příčina  
 Volání metody GetHashCode typu jsou podstatnou část data profilování nebo metodu přidělí paměť.  
  
## <a name="rule-description"></a>Popis pravidla  
 Použití algoritmu hash je technika pro rychlé vyhledávání konkrétní položky v kolekci velké. Protože hash – tabulky může být velmi velké a nepotřebujete podporovat velké objemy přístup, musí být velmi efektivní zatřiďovacích tabulkách. Vyplývá tento požadavek je, že GetHashCode metody v rozhraní .NET Framework by neměla přidělit paměť. Přidělování paměti zvyšuje zatížení systému uvolňování paměti a zpřístupní metodu potenciální způsobuje prodlevy, pokud se stát, že bude nutné spustit uvolňování paměti v důsledku požadavek na přidělení.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Snížit složitost metody.