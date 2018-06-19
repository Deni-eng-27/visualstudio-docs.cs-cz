---
title: 'CA1714: Výčty příznaků by neměly mít názvy v množném čísle'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- FlagsEnumsShouldHavePluralNames
- CA1714
helpviewer_keywords:
- CA1714
- FlagsEnumsShouldHavePluralNames
ms.assetid: 95ef5b43-7681-49e9-a5a3-ac0357cf1be7
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1e00c0e7eaf3b88588f0914d78a23db40082d63f
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31915728"
---
# <a name="ca1714-flags-enums-should-have-plural-names"></a>CA1714: Výčty příznaků by neměly mít názvy v množném čísle
|||
|-|-|
|TypeName|FlagsEnumsShouldHavePluralNames|
|CheckId|CA1714|
|Kategorie|Microsoft.Naming|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Veřejný výčet má <xref:System.FlagsAttribute?displayProperty=fullName> a jeho název nemá na konci v na '.

## <a name="rule-description"></a>Popis pravidla
 Typy, které jsou označené <xref:System.FlagsAttribute> mít názvy, které jsou v množném čísle, protože atribut uvádí, zda lze zadat více než jednu hodnotu. Například výčet, který definuje dny v týdnu, může být určena pro použití v aplikaci, kde můžete určit více dní. Tento výčet by měl mít <xref:System.FlagsAttribute> a může být volána 'dny. Podobně jako výčet, který umožňuje zadat pouze jeden den by mít atribut a může být volána "Den".

 Zásady vytváření názvů zadejte obecný vzhled pro knihovny cílené modul common language runtime. Tím se snižuje křivky learning, který je vyžadován pro nové knihovny softwaru a zvyšuje sebejistotu zákazníka, knihovny byla vyvinuta uživatelem s odbornými znalostmi v vývoj spravovaného kódu.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Zkontrolujte název výčtu množném čísle slovo nebo odebrat <xref:System.FlagsAttribute> atribut Pokud více hodnot výčtu by neměl být určen současně.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Je bezpečné potlačit narušení, pokud název množném čísle word, ale nemá příponu na '. Například pokud výčet násobek dne, který je popsáno dříve byly s názvem 'DaysOfTheWeek', by porušení logice pravidla, ale ne jeho záměr. Takové porušení by měl být suppressd.

## <a name="related-rules"></a>Související pravidla
 [CA1027: Označte výčty pomocí FlagsAttribute](../code-quality/ca1027-mark-enums-with-flagsattribute.md)

 [CA2217: Neoznačujte výčty pomocí FlagsAttribute](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)

## <a name="see-also"></a>Viz také
 <xref:System.FlagsAttribute?displayProperty=fullName> [Návrh výčtu](/dotnet/standard/design-guidelines/enum)