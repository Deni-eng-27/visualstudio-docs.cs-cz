---
title: 'CA2131: Typy kritické pro zabezpečení nemusejí podporovat účast na ekvivalenci typů | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA2131
ms.assetid: 4170f3b1-6086-430d-8fba-837d5538c573
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 551c0bd73abb2d42f2673dfcc57153b957bcbcbc
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="ca2131-security-critical-types-may-not-participate-in-type-equivalence"></a>CA2131: Typy kritické pro zabezpečení nemusejí podporovat účast na ekvivalenci typů
|||  
|-|-|  
|TypeName|CriticalTypesMustNotParticipateInTypeEquivalence|  
|CheckId|CA2131|  
|Kategorie|Microsoft.Security|  
|Narušující změna|Narušující|  
  
## <a name="cause"></a>příčina  
 Typ účastní ekvivalence typů a buď vlastní typ nebo člen nebo pole typu, je označené <xref:System.Security.SecurityCriticalAttribute> atribut.  
  
## <a name="rule-description"></a>Popis pravidla  
 Toto pravidlo je vyvoláno pro všechny kritické typy nebo typy obsahující kritické metody nebo pole, která se účastní porovnávání typů. Zjistí-li modulu CLR takového typu, se nepodaří načíst s <xref:System.TypeLoadException> za běhu. Obvykle ke spuštění tohoto pravidla dochází pouze v případě, že uživatel implementuje porovnávání typů ručně a nepřenechává porovnávání typů na nástroji tlbimp a kompilátorech.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení toto pravidlo, odeberte atribut SecurityCritical.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění na toto pravidlo.  
  
## <a name="example"></a>Příklad  
 Následující příklady ukazují, rozhraní, metodu a pole, které způsobí, že toto pravidlo má provést.  
  
 [!code-csharp[FxCop.Security.CA2131.CriticalTypesMustNotParticipateInTypeEquivalence#1](../code-quality/codesnippet/CSharp/ca2131-security-critical-types-may-not-participate-in-type-equivalence_1.cs)]  
  
## <a name="see-also"></a>Viz také  
 [Kód transparentní pro zabezpečení, úroveň 2](/dotnet/framework/misc/security-transparent-code-level-2)