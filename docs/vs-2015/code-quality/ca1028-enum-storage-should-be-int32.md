---
title: 'CA1028: enum Storage by měl být Int32 | Microsoft Docs'
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
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: fc1039cb547a48c4f2dd3ea869b46d4706e9c3a2
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/19/2019
ms.locfileid: "72661908"
---
# <a name="ca1028-enum-storage-should-be-int32"></a>CA1028: Úložiště výčtu by měl být Int32
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|EnumStorageShouldBeInt32|
|CheckId|CA1028|
|Kategorie|Microsoft. Design|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Nadřízený typ veřejného výčtu není <xref:System.Int32?displayProperty=fullName>.

## <a name="rule-description"></a>Popis pravidla
 Výčet je typ hodnoty, který definuje množinu souvisejících pojmenovaných konstant. Ve výchozím nastavení se k uložení konstantní hodnoty používá datový typ <xref:System.Int32?displayProperty=fullName>. I když tento základní typ můžete změnit, není nutné ani se pro většinu scénářů doporučuje. Počítejte s tím, že nedosáhnete významného nárůstu výkonu pomocí datového typu, který je menší než <xref:System.Int32>. Pokud nemůžete použít výchozí datový typ, měli byste použít jeden z celočíselných typů kompatibilních se specifikací CLS, <xref:System.Byte>, <xref:System.Int16>, <xref:System.Int32> nebo <xref:System.Int64>, abyste se ujistili, že všechny hodnoty výčtu mohou být reprezentovány v programování kompatibilním se specifikací CLS. jazyky.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Pokud chcete opravit porušení tohoto pravidla, pokud neexistují problémy s velikostí nebo kompatibilitou, použijte <xref:System.Int32>. V situacích, kdy <xref:System.Int32> není dostatečně velká pro uložení hodnot, použijte <xref:System.Int64>. Pokud zpětné kompatibility vyžaduje menší datový typ, použijte <xref:System.Byte> nebo <xref:System.Int16>.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Potlačí upozornění z tohoto pravidla pouze v případě, že to vyžaduje problémy s zpětnou kompatibilitou. V aplikacích není selhání při dodržení tohoto pravidla obvykle způsobeno problémy. V knihovnách, kde je třeba vzájemná funkční spolupráce jazyků, neúspěšná nedodržení tohoto pravidla může negativně ovlivnit vaše uživatele.

## <a name="example-of-a-violation"></a>Příklad porušení

### <a name="description"></a>Popis
 Následující příklad ukazuje dva výčty, které nepoužívají doporučený podkladový datový typ.

### <a name="code"></a>Kód
 [!code-csharp[FxCop.Design.EnumIntegralType#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.EnumIntegralType/cs/FxCop.Design.EnumIntegralType.cs#1)]
 [!code-vb[FxCop.Design.EnumIntegralType#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.EnumIntegralType/vb/FxCop.Design.EnumIntegralType.vb#1)]

## <a name="example-of-how-to-fix"></a>Příklad opravy

### <a name="description"></a>Popis
 Následující příklad opravuje předchozí porušení změnou podkladového datového typu na <xref:System.Int32>.

### <a name="code"></a>Kód
 [!code-csharp[FxCop.Design.EnumIntegralTypeFixed#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.EnumIntegralTypeFixed/cs/FxCop.Design.EnumIntegralTypeFixed.cs#1)]
 [!code-vb[FxCop.Design.EnumIntegralTypeFixed#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.EnumIntegralTypeFixed/vb/FxCop.Design.EnumIntegralTypeFixed.vb#1)]

## <a name="related-rules"></a>Související pravidla
 [CA1008: Výčty by měly mít nulovou hodnotu](../code-quality/ca1008-enums-should-have-zero-value.md)

 [CA1027: Označte výčty pomocí FlagsAttribute](../code-quality/ca1027-mark-enums-with-flagsattribute.md)

 [CA2217: Neoznačujte výčty pomocí FlagsAttribute](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)

 [CA1700: Nepojmenovávejte výčty hodnot Reserved](../code-quality/ca1700-do-not-name-enum-values-reserved.md)

 [CA1712: Nezačínejte hodnoty výčtu s názvem typu](../code-quality/ca1712-do-not-prefix-enum-values-with-type-name.md)

## <a name="see-also"></a>Viz také
 <xref:System.Byte?displayProperty=fullName><xref:System.Int16?displayProperty=fullName>
 <xref:System.Int32?displayProperty=fullName>
 <xref:System.Int64?displayProperty=fullName>
