---
title: 'DA0001: použít StringBuilder pro zřetězení | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
f1_keywords:
- vs.performance.DA0001
- vs.performance.rules.DAUseStringBuilder
- vs.performance.1
- vs.performance.rules.DA0001
ms.assetid: a7cc7613-ad5f-48c8-bd2b-56372cc12dfc
caps.latest.revision: 19
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: faa0cf18bfd9810d84e01028b3f787b3b2c99578
ms.sourcegitcommit: c150d0be93b6f7ccbe9625b41a437541502560f5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2020
ms.locfileid: "75844747"
---
# <a name="da0001-use-stringbuilder-for-concatenations"></a>DA0001: Pro zřetězování používejte StringBuilder
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější dokumentaci k sadě Visual Studio naleznete v tématu [DA0001: použití StringBuilder pro zřetězení](https://docs.microsoft.com/visualstudio/profiling/da0001-use-stringbuilder-for-concatenations).  
  
|||  
|-|-|  
|Id pravidla|DA0001|  
|Kategorie|Využití .NET Framework|  
|Metody profilace|Vzorkování<br /><br /> Instrumentace|  
|Zpráva|Zvažte použití StringBuilder pro zřetězení řetězců.|  
|Typ zprávy|Upozornění|  
  
## <a name="cause"></a>příčina  
 Volání System. String. Concat představují významnou část dat profilování. Zvažte použití třídy <xref:System.Text.StringBuilder> pro vytváření řetězců z více segmentů.  
  
## <a name="rule-description"></a>Popis pravidla  
 Objekt <xref:System.String> je neměnný. Proto jakákoli úprava řetězce vytvoří nový objekt String a uvolňování paměti původní. Toto chování je stejné, bez ohledu na to, zda voláte řetězec. Concat explicitně, nebo použijte operátory zřetězení řetězců, například + nebo + =.. Výkon programu se může snížit, pokud jsou tyto metody často volány, například když jsou znaky přidány do řetězce v těsné smyčce.  
  
 Třída StringBuilder je proměnlivý objekt, a na rozdíl od System. String, většina metod v StringBuilder, která upravuje instanci této třídy, vrátí odkaz na stejnou instanci. Můžete vložit znaky nebo připojit text k instanci StringBuilder a odebrat nebo nahradit znaky v instanci bez nutnosti přidělit novou instanci a odstraněním původní instance.  
  
## <a name="how-to-investigate-a-warning"></a>Jak prozkoumat upozornění  
 Dvakrát klikněte na zprávu v okně Seznam chyb, abyste přešli na [zobrazení podrobností o funkcích](../profiling/function-details-view.md) profilu vzorkování. Najděte části programu, které zjednodušují zřetězení řetězců. Použijte třídu StringBuilder pro komplexní manipulaci s řetězci, včetně častých operací zřetězení řetězců.  
  
 Další informace o tom, jak pracovat s řetězci, najdete v části [operace s řetězci](https://msdn.microsoft.com/library/ms998547.aspx#scalenetchapt05_topic26) v [kapitole 5 – zlepšení výkonu spravovaného kódu](https://msdn.microsoft.com/library/ms998547.aspx) v knihovně Microsoft Patterns and Practices Library.
