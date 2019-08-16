---
title: 'CA2231: Přetižte operátor rovnosti při přetížení ValueType.Equals'
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- OverloadOperatorEqualsOnOverridingValueTypeEquals
- CA2231
- OverrideOperatorEqualsOnOverridingValueTypeEquals
helpviewer_keywords:
- OverloadOperatorEqualsOnOverridingValueTypeEquals
- CA2231
ms.assetid: 114c0161-261a-40ad-8b2c-0932d6909d2a
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: fafa4782762e18f1ced8c7f929720e995986ac7a
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/16/2019
ms.locfileid: "69546864"
---
# <a name="ca2231-overload-operator-equals-on-overriding-valuetypeequals"></a>CA2231: Přetižte operátor rovnosti při přetížení ValueType.Equals

|||
|-|-|
|TypeName|OverloadOperatorEqualsOnOverridingValueTypeEquals|
|CheckId|CA2231|
|Kategorie|Microsoft.Usage|
|Narušující změna|Bez přerušení|

## <a name="cause"></a>příčina

Hodnotový typ přepisuje <xref:System.Object.Equals%2A?displayProperty=fullName> , ale neimplementuje operátor rovnosti.

Ve výchozím nastavení toto pravidlo vyhledává pouze externě viditelné typy, ale je možné jej [nakonfigurovat](#configurability).

## <a name="rule-description"></a>Popis pravidla

Ve většině programovacích jazyků neexistuje žádná výchozí implementace operátoru rovnosti (= =) pro typy hodnot. Pokud váš programovací jazyk podporuje přetížení operátorů, měli byste uvažovat o implementaci operátoru rovnosti. Chování by mělo být stejné jako u <xref:System.Object.Equals%2A>.

Nelze použít výchozí operátor rovnosti v přetížené implementaci operátoru rovnosti. Uděláte to tak, že dojde k přetečení zásobníku. K implementaci operátoru rovnosti použijte metodu Object. Equals v implementaci. Příklad:

```vb
If (Object.ReferenceEquals(left, Nothing)) Then
    Return Object.ReferenceEquals(right, Nothing)
Else
    Return left.Equals(right)
End If
```

```csharp
if (Object.ReferenceEquals(left, null))
    return Object.ReferenceEquals(right, null);
return left.Equals(right);
```

## <a name="how-to-fix-violations"></a>Jak opravit porušení

Chcete-li opravit porušení tohoto pravidla, implementujte operátor rovnosti.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Je bezpečné potlačit upozornění od tohoto pravidla; Nicméně doporučujeme, abyste zadali operátor rovnosti, pokud je to možné.

## <a name="configurability"></a>Konfigurovatelnost

Pokud toto pravidlo spouštíte z [analyzátorů FxCop](install-fxcop-analyzers.md) (a ne pomocí starší verze analýzy), můžete nakonfigurovat, které části základu kódu mají spustit toto pravidlo, na základě jejich přístupnosti. Například chcete-li určit, že pravidlo by mělo běžet pouze proti neveřejnému povrchu rozhraní API, přidejte do souboru. editorconfig v projektu následující dvojici klíč-hodnota:

```ini
dotnet_code_quality.ca2231.api_surface = private, internal
```

Tuto možnost můžete nakonfigurovat jenom pro toto pravidlo, pro všechna pravidla nebo pro všechna pravidla v této kategorii (použití). Další informace najdete v tématu [Konfigurace analyzátorů FxCop](configure-fxcop-analyzers.md).

## <a name="example"></a>Příklad

Následující příklad definuje typ, který je v rozporu s tímto pravidlem:

[!code-csharp[FxCop.Usage.EqualsGetHashCode#1](../code-quality/codesnippet/CSharp/ca2231-overload-operator-equals-on-overriding-valuetype-equals_1.cs)]

## <a name="related-rules"></a>Související pravidla

- [CA1046: Nepřetížit operátor přetížení se rovná na odkazových typech](../code-quality/ca1046-do-not-overload-operator-equals-on-reference-types.md)
- [CA2225: Přetížení operátoru mají pojmenované alternativy.](../code-quality/ca2225-operator-overloads-have-named-alternates.md)
- [CA2226 Operátory by měly mít symetrické přetížení](../code-quality/ca2226-operators-should-have-symmetrical-overloads.md)
- [CA2224: Přepište Equals při přetížení operátoru Equals](../code-quality/ca2224-override-equals-on-overloading-operator-equals.md)
- [CA2218: Přepsat GetHashCode při přepsání Equals](../code-quality/ca2218-override-gethashcode-on-overriding-equals.md)

## <a name="see-also"></a>Viz také:

- <xref:System.Object.Equals%2A?displayProperty=fullName>