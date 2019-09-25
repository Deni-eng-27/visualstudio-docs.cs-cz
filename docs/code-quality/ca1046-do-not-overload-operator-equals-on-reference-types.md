---
title: 'CA1046: Nepřetěžujte operátory rovnosti u odkazových typů'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- DoNotOverloadOperatorEqualsOnReferenceTypes
- CA1046
helpviewer_keywords:
- CA1046
- DoNotOverloadOperatorEqualsOnReferenceTypes
ms.assetid: c1dfbfe3-63f9-4005-a81a-890427b77e79
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 23358d104c891ff9e230f0daad0f5e6ca57b46c2
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/24/2019
ms.locfileid: "71235769"
---
# <a name="ca1046-do-not-overload-operator-equals-on-reference-types"></a>CA1046: Nepřetěžujte operátory rovnosti u odkazových typů

|||
|-|-|
|TypeName|DoNotOverloadOperatorEqualsOnReferenceTypes|
|CheckId|CA1046|
|Kategorie|Microsoft.Design|
|Zásadní změna|Narušující|

## <a name="cause"></a>příčina
Veřejný nebo vnořený typ veřejného odkazu přetěžuje operátor rovnosti.

## <a name="rule-description"></a>Popis pravidla
U referenčních typů je výchozí implementace operátoru rovnosti téměř vždy správná. Ve výchozím nastavení jsou dva odkazy rovny, pouze pokud ukazují na stejný objekt.

## <a name="how-to-fix-violations"></a>Jak opravit porušení
Chcete-li opravit porušení tohoto pravidla, odeberte implementaci operátoru rovnosti.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
Je bezpečné potlačit upozornění od tohoto pravidla, pokud se typ odkazu chová jako vestavěný typ hodnoty. Pokud je smysluplné provést sčítání nebo odčítání na instancích typu, je pravděpodobně správné implementovat operátor rovnosti a potlačit porušení.

## <a name="example"></a>Příklad
Následující příklad ukazuje výchozí chování při porovnávání dvou odkazů.

[!code-csharp[FxCop.Design.RefTypesNoEqualityOp#1](../code-quality/codesnippet/CSharp/ca1046-do-not-overload-operator-equals-on-reference-types_1.cs)]

## <a name="example"></a>Příklad

Následující aplikace porovnává některé odkazy.

[!code-csharp[FxCop.Design.TestRefTypesNoEqualityOp#1](../code-quality/codesnippet/CSharp/ca1046-do-not-overload-operator-equals-on-reference-types_2.cs)]

Tento příklad vytvoří následující výstup:

```txt
a = new (2,2) and b = new (2,2) are equal? No
c and a are equal? Yes
b and a are == ? No
c and a are == ? Yes
```

## <a name="related-rules"></a>Související pravidla

[CA1013: Operátor přetížení se rovná při přetížení metody sčítání a odečítání.](../code-quality/ca1013-overload-operator-equals-on-overloading-add-and-subtract.md)

## <a name="see-also"></a>Viz také:

- <xref:System.Object.Equals%2A?displayProperty=fullName>
- [Operátory rovnosti](/dotnet/standard/design-guidelines/equality-operators)