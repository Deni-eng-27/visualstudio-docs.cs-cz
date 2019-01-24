---
title: 'CA1028: Úložiště výčtu by měl být Int32 | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1028
- EnumStorageShouldBeInt32
helpviewer_keywords:
- EnumStorageShouldBeInt32
- CA1028
ms.assetid: 87160825-9f39-4142-8d7f-a31fe7ac7b84
caps.latest.revision: 21
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: e79eb7e0ed33184103cc772c13515959cf973ecc
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54783702"
---
# <a name="ca1028-enum-storage-should-be-int32"></a>CA1028: Úložiště výčtu by mělo být Int32
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|EnumStorageShouldBeInt32|
|CheckId|CA1028|
|Kategorie|Microsoft.Design|
|Narušující změna|Narušující|

## <a name="cause"></a>Příčina
 Základní typ veřejný výčet není <xref:System.Int32?displayProperty=fullName>.

## <a name="rule-description"></a>Popis pravidla
 Výčet je typ hodnoty, který definuje množinu souvisejících pojmenovaných konstant. Ve výchozím nastavení <xref:System.Int32?displayProperty=fullName> datový typ se používá pro uložení konstantní hodnoty. I když toto můžete změnit základní typ, není nutné nebo doporučené pro většinu scénářů. Všimněte si, že žádné zvýšení výkonu můžete dosáhnout použitím datový typ, který je menší než <xref:System.Int32>. Pokud nemůžete použít výchozí typ dat, měli byste použít jeden z systému CLS (Common Language)-kompatibilní celočíselných typů <xref:System.Byte>, <xref:System.Int16>, <xref:System.Int32>, nebo <xref:System.Int64> abyste měli jistotu, že všechny hodnoty výčtu lze znázornit v Kompatibilní se Specifikací CLS programovacích jazyků.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, pokud existují problémy velikost nebo kompatibility, použijte <xref:System.Int32>. Pro situace, kdy <xref:System.Int32> není dostatečně velký pro uložení hodnot, použijte <xref:System.Int64>. Pokud zpětné kompatibility vyžaduje menší datový typ, použijte <xref:System.Byte> nebo <xref:System.Int16>.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Potlačit upozornění tohoto pravidla, pouze pokud to vyžaduje problémům se zpětnou kompatibilitou. V aplikacích selhání pro dosažení souladu s tímto pravidlem obvykle nezpůsobí potíže. V knihovnách, ve kterém jsou vyžadována vzájemná funkční spolupráce jazyka, nedodržení tohoto pravidla může nepříznivě ovlivnit vaši uživatelé.

## <a name="example-of-a-violation"></a>Příkladem porušení

### <a name="description"></a>Popis
 Následující příklad ukazuje dva výčty, které nepoužívají doporučené příslušný datový typ.

### <a name="code"></a>Kód
 [!code-csharp[FxCop.Design.EnumIntegralType#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.EnumIntegralType/cs/FxCop.Design.EnumIntegralType.cs#1)]
 [!code-vb[FxCop.Design.EnumIntegralType#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.EnumIntegralType/vb/FxCop.Design.EnumIntegralType.vb#1)]

## <a name="example-of-how-to-fix"></a>Příklad, jak k opravě

### <a name="description"></a>Popis
 Následující příklad opravuje předchozí porušení změnou základní datový typ na <xref:System.Int32>.

### <a name="code"></a>Kód
 [!code-csharp[FxCop.Design.EnumIntegralTypeFixed#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.EnumIntegralTypeFixed/cs/FxCop.Design.EnumIntegralTypeFixed.cs#1)]
 [!code-vb[FxCop.Design.EnumIntegralTypeFixed#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.EnumIntegralTypeFixed/vb/FxCop.Design.EnumIntegralTypeFixed.vb#1)]

## <a name="related-rules"></a>Související pravidla
 [CA1008: Výčty by měly mít nulovou hodnotu](../code-quality/ca1008-enums-should-have-zero-value.md)

 [CA1027: Označte výčty pomocí FlagsAttribute](../code-quality/ca1027-mark-enums-with-flagsattribute.md)

 [CA2217: Neoznačujte výčty pomocí FlagsAttribute](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)

 [CA1700: Nepojmenovávejte výčtu hodnoty 'Reserved'](../code-quality/ca1700-do-not-name-enum-values-reserved.md)

 [CA1712: Nezačínejte hodnoty výčtu s názvem typu](../code-quality/ca1712-do-not-prefix-enum-values-with-type-name.md)

## <a name="see-also"></a>Viz také
 <xref:System.Byte?displayProperty=fullName><xref:System.Int16?displayProperty=fullName>
 <xref:System.Int32?displayProperty=fullName>
 <xref:System.Int64?displayProperty=fullName>
