---
title: "CA1064: Výjimky by měly být veřejné | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1064
- ExceptionsShouldBePublic
helpviewer_keywords:
- ExceptionsShouldBePublic
- CA1064
ms.assetid: 83eb224c-2456-4368-acf4-3b3378e67759
caps.latest.revision: "11"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 7779be831b32572addb6198b5a5be46616cdb1b4
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="ca1064-exceptions-should-be-public"></a>CA1064: Výjimky by měly být veřejné
|||  
|-|-|  
|TypeName|ExceptionsShouldBePublic|  
|CheckId|CA1064|  
|Kategorie|Microsoft.Design|  
|Narušující změna|Bez ukončování řádků|  
  
## <a name="cause"></a>příčina  
 Výjimka neveřejný odvozena přímo z <xref:System.Exception>, <xref:System.SystemException>, nebo <xref:System.ApplicationException>.  
  
## <a name="rule-description"></a>Popis pravidla  
 Vnitřní výjimkou je jenom viditelné v její vlastní interní oboru. Jakmile výjimka přesáhne hranice vnitřního rozsahu, lze pro zachycení výjimky použít pouze základní výjimku. Pokud je zděděn vnitřní výjimku z <xref:System.Exception>, <xref:System.SystemException>, nebo <xref:System.ApplicationException>, kód externí nebude mít dostatečné informace k vědět, co dělat s výjimkou.  
  
 Ale pokud kód veřejné výjimka, která později slouží jako základ pro vnitřní výjimku, je možné logicky předpokládat, že další kód se bude moct dělat něco inteligentního s výjimkou základní. Další informace, než je zadán T:System.Exception, T:System.SystemException nebo T:System.ApplicationException bude mít veřejné výjimka.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Zveřejnit výjimku a vnitřní výjimku z veřejné výjimky, který není odvozen <xref:System.Exception>, <xref:System.SystemException>, nebo <xref:System.ApplicationException>.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Zprávu od toto pravidlo potlačit, pokud jste si jistí ve všech případech, že privátní výjimka bude zachycena v rámci vlastní interní oboru.  
  
## <a name="example"></a>Příklad  
 Toto pravidlo aktivuje v prvním příkladu metoda FirstCustomException, protože třída výjimky je odvozena přímo z výjimky a je interní. Pravidlo k třídě SecondCustomException neaktivuje, protože Přestože třída je odvozen také přímo z výjimky, je třída deklarována veřejné. Třída třetí také neaktivuje pravidlo protože neodvozuje přímo z <xref:System.Exception?displayProperty=fullName>, <xref:System.SystemException?displayProperty=fullName>, nebo <xref:System.ApplicationException?displayProperty=fullName>.  
  
 [!code-csharp[FxCop.Design.ExceptionsShouldBePublic.CA1064#1](../code-quality/codesnippet/CSharp/ca1064-exceptions-should-be-public_1.cs)]