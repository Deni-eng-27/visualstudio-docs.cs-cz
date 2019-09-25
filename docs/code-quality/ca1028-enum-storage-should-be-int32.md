---
title: 'CA1028: Úložiště výčtu by mělo být Int32'
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- CA1028
- EnumStorageShouldBeInt32
helpviewer_keywords:
- EnumStorageShouldBeInt32
- CA1028
ms.assetid: 87160825-9f39-4142-8d7f-a31fe7ac7b84
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 47a934a6e35296927eea64465ff8e7007219bec5
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/24/2019
ms.locfileid: "71236086"
---
# <a name="ca1028-enum-storage-should-be-int32"></a>CA1028: Úložiště výčtu by mělo být Int32

|||
|-|-|
|TypeName|EnumStorageShouldBeInt32|
|CheckId|CA1028|
|Kategorie|Microsoft.Design|
|Zásadní změna|Narušující|

## <a name="cause"></a>příčina

Podkladový typ výčtu není <xref:System.Int32?displayProperty=fullName>.

Ve výchozím nastavení toto pravidlo vyhledává pouze veřejné výčty, ale je možné jej [nakonfigurovat](#configurability).

## <a name="rule-description"></a>Popis pravidla

Výčet je typ hodnoty, který definuje množinu souvisejících pojmenovaných konstant. Ve výchozím nastavení <xref:System.Int32?displayProperty=fullName> je datový typ použit k uložení hodnoty konstanty. I když tento základní typ můžete změnit, není nutné ani se pro většinu scénářů doporučuje. Nemusíte dosáhnout významného nárůstu výkonu pomocí datového typu, který je <xref:System.Int32>menší než. Pokud nemůžete použít výchozí datový typ, měli byste použít jeden z integrálních typů kompatibilních se specifikací CLS (Common Language System <xref:System.Byte>) <xref:System.Int16>, <xref:System.Int32>,, <xref:System.Int64> nebo k zajištění, aby všechny hodnoty výčtu mohly být zastoupeny v Programovací jazyky kompatibilní se specifikací CLS.

## <a name="how-to-fix-violations"></a>Jak opravit porušení

Chcete-li opravit porušení tohoto pravidla, pokud neexistují problémy s velikostí nebo kompatibilitou, použijte <xref:System.Int32>. V situacích, <xref:System.Int32> kdy není dostatečná velikost pro uložení hodnot, použijte. <xref:System.Int64> Pokud zpětné kompatibility vyžaduje menší datový typ, použijte <xref:System.Byte> nebo. <xref:System.Int16>

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Potlačí upozornění z tohoto pravidla pouze v případě, že to vyžaduje problémy s zpětnou kompatibilitou. V aplikacích není selhání při dodržení tohoto pravidla obvykle způsobeno problémy. V knihovnách, kde je třeba vzájemná funkční spolupráce jazyků, neúspěšná nedodržení tohoto pravidla může negativně ovlivnit vaše uživatele.

## <a name="configurability"></a>Konfigurovatelnost

Pokud toto pravidlo spouštíte z [analyzátorů FxCop](install-fxcop-analyzers.md) (a ne pomocí starší verze analýzy), můžete nakonfigurovat, které části základu kódu mají spustit toto pravidlo, na základě jejich přístupnosti. Například chcete-li určit, že pravidlo by mělo běžet pouze proti neveřejnému povrchu rozhraní API, přidejte do souboru. editorconfig v projektu následující dvojici klíč-hodnota:

```ini
dotnet_code_quality.ca1028.api_surface = private, internal
```

Tuto možnost můžete nakonfigurovat jenom pro toto pravidlo, pro všechna pravidla nebo pro všechna pravidla v této kategorii (návrh). Další informace najdete v tématu [Konfigurace analyzátorů FxCop](configure-fxcop-analyzers.md).

## <a name="example-of-a-violation"></a>Příklad porušení

Následující příklad ukazuje dva výčty, které nepoužívají doporučený podkladový datový typ.

[!code-vb[FxCop.Design.EnumIntegralType#1](../code-quality/codesnippet/VisualBasic/ca1028-enum-storage-should-be-int32_1.vb)]
[!code-csharp[FxCop.Design.EnumIntegralType#1](../code-quality/codesnippet/CSharp/ca1028-enum-storage-should-be-int32_1.cs)]

## <a name="example-of-how-to-fix"></a>Příklad opravy

Následující příklad opravuje předchozí porušení změnou základního datového typu na <xref:System.Int32>.

[!code-csharp[FxCop.Design.EnumIntegralTypeFixed#1](../code-quality/codesnippet/CSharp/ca1028-enum-storage-should-be-int32_2.cs)]
[!code-vb[FxCop.Design.EnumIntegralTypeFixed#1](../code-quality/codesnippet/VisualBasic/ca1028-enum-storage-should-be-int32_2.vb)]

## <a name="related-rules"></a>Související pravidla

- [CA1008 Výčty by měly mít nulovou hodnotu](../code-quality/ca1008-enums-should-have-zero-value.md)
- [CA1027: Označení výčtů pomocí FlagsAttribute](../code-quality/ca1027-mark-enums-with-flagsattribute.md)
- [CA2217: Neoznačujte výčty pomocí FlagsAttribute](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)
- [CA1700: Nejmenujte hodnoty výčtu ' rezervované '](../code-quality/ca1700-do-not-name-enum-values-reserved.md)
- [CA1712: Neprefixovat hodnoty výčtu s názvem typu](../code-quality/ca1712-do-not-prefix-enum-values-with-type-name.md)

## <a name="see-also"></a>Viz také:

- <xref:System.Byte?displayProperty=fullName>
- <xref:System.Int16?displayProperty=fullName>
- <xref:System.Int32?displayProperty=fullName>
- <xref:System.Int64?displayProperty=fullName>