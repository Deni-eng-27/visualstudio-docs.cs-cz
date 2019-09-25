---
title: 'CA2130: Konstanty kritické pro zabezpečení musí být transparentní'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2130
ms.assetid: 344c7f7b-9130-4675-ae7f-9fa260cc9789
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 62cf9b6b62dac85251d9fca434b35f0a7c6254c7
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/24/2019
ms.locfileid: "71232424"
---
# <a name="ca2130-security-critical-constants-should-be-transparent"></a>CA2130: Konstanty kritické pro zabezpečení musí být transparentní

|||
|-|-|
|TypeName|ConstantsShouldBeTransparent|
|CheckId|CA2130|
|Kategorie|Microsoft.Security|
|Zásadní změna|Narušující|

## <a name="cause"></a>příčina
Pole konstanty nebo člen výčtu je označeno atributem <xref:System.Security.SecurityCriticalAttribute>.

## <a name="rule-description"></a>Popis pravidla
Pro konstantní hodnoty není vynucována transparentnost, protože kompilátory vkládají konstantní hodnoty do kódu, aby za běhu programu nebylo zapotřebí žádné vyhledávání. Konstantní pole by měla být transparentní z pohledu zabezpečení, aby kontroloři kódu nepředpokládali, že transparentní kód nemůže ke konstantě přistoupit.

## <a name="how-to-fix-violations"></a>Jak opravit porušení
Chcete-li opravit porušení tohoto pravidla, odeberte atribut SecurityCritical z pole nebo hodnoty.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
Nepotlačujte upozornění na toto pravidlo.

## <a name="example"></a>Příklad
V následujících příkladech je hodnota `EnumWithCriticalValues.CriticalEnumValue` výčtu a konstanta `CriticalConstant` vyvolána tímto upozorněním. Chcete-li tyto problémy vyřešit, odeberte`SecurityCritical`atribut [], aby byly jeho zabezpečení transparentní.

[!code-csharp[FxCop.Security.CA2130.ConstantsShouldBeTransparent#1](../code-quality/codesnippet/CSharp/ca2130-security-critical-constants-should-be-transparent_1.cs)]