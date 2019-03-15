---
title: 'CA1717: Pouze výčty FlagsAttribute by měly mít názvy v množném čísle'
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- CA1717
- OnlyFlagsEnumsShouldHavePluralNames
helpviewer_keywords:
- OnlyFlagsEnumsShouldHavePluralNames
- CA1717
ms.assetid: a6855d8b-d78a-42c1-834e-61c31f5572ed
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e6da5a791237aefa037b2cb16bffef34576ac6e7
ms.sourcegitcommit: f7c401a376ce410336846835332a693e6159c551
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/14/2019
ms.locfileid: "57869860"
---
# <a name="ca1717-only-flagsattribute-enums-should-have-plural-names"></a>CA1717: Pouze výčty FlagsAttribute by měly mít názvy v množném čísle

|||
|-|-|
|TypeName|OnlyFlagsEnumsShouldHavePluralNames|
|CheckId|CA1717|
|Kategorie|Microsoft.Naming|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina

Název výčtu končí v množném čísle word a výčet není označen atributem <xref:System.FlagsAttribute?displayProperty=fullName> atribut.

Ve výchozím nastavení, toto pravidlo pouze vypadá v externě viditelné výčtů, ale je to [konfigurovatelné](#configurability).

## <a name="rule-description"></a>Popis pravidla

Zásady vytváření názvů diktovat, že název v množném čísle pro výčet udává, že více než jednu hodnotu výčtu lze zadat současně. <xref:System.FlagsAttribute> Říká kompilátoru, že výčet mají být považována za bitové pole, který umožňuje bitové operace výčtu.

Pokud pouze najednou můžete zadat jednu hodnotu výčtu, název výčtu by měl být singulární aplikace word. Například výčet, který definuje dny v týdnu může být určena pro použití v aplikaci ve kterém můžete zadat více dní. By měl mít tento výčet <xref:System.FlagsAttribute> a může mít název "dny. Podobně jako výčet, který umožňuje zadat pouze jeden den by obsahovat atribut a může být volána "Den".

Zásady vytváření názvů poskytují obecný vzhled knihovnám využívajících common language runtime. To snižuje čas, který se vyžaduje další nové knihovny softwaru a zvyšuje důvěru zákazníků, že byla vyvinuta knihovny někdo, kdo má odborných znalostí v vývoj spravovaného kódu.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

Nastavit název výčtu singulární slova nebo přidat <xref:System.FlagsAttribute>.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Je bezpečné potlačit upozornění pravidla, je-li název končí v jednotném čísle aplikace word.

## <a name="configurability"></a>Možnosti konfigurace:

Pokud používáte systém toto pravidlo z [analyzátory FxCop](install-fxcop-analyzers.md) (a ne prostřednictvím statickou analýzu kódu), které části můžete nakonfigurovat vašeho základu kódu pro toto pravidlo spouštět, v závislosti na jejich přístupnost. Například k určení, že se má pravidlo spustit jenom na povrchu neveřejné rozhraní API, přidejte následující dvojice klíč hodnota do souboru .editorconfig ve vašem projektu:

```
dotnet_code_quality.ca1717.api_surface = private, internal
```

Tuto možnost pro právě toto pravidlo, všechna pravidla nebo pro všechna pravidla můžete konfigurovat v této kategorii (zásady). Další informace najdete v tématu [analyzátory FxCop konfigurace](configure-fxcop-analyzers.md).

## <a name="related-rules"></a>Související pravidla

- [CA1714: Výčty příznaků by neměly mít názvy v množném čísle](../code-quality/ca1714-flags-enums-should-have-plural-names.md)
- [CA1027: Označte výčty pomocí FlagsAttribute](../code-quality/ca1027-mark-enums-with-flagsattribute.md)
- [CA2217: Neoznačujte výčty pomocí FlagsAttribute](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)

## <a name="see-also"></a>Viz také:

- <xref:System.FlagsAttribute?displayProperty=fullName>
- [Návrh výčtu](/dotnet/standard/design-guidelines/enum)