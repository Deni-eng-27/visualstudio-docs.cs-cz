---
title: 'CA1006: Nevnořujte obecné typy do signatur členu'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- DoNotNestGenericTypesInMemberSignatures
- CA1006
helpviewer_keywords:
- CA1006
- DoNotNestGenericTypesInMemberSignatures
ms.assetid: dfc867bc-f4af-45d7-b071-db04a248f9fc
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 72d75985482ebf7e90db9d817212882b5ed8c292
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55928462"
---
# <a name="ca1006-do-not-nest-generic-types-in-member-signatures"></a>CA1006: Nevnořujte obecné typy do signatur členu

|||
|-|-|
|TypeName|DoNotNestGenericTypesInMemberSignatures|
|CheckId|CA1006|
|Kategorie|Microsoft.Design|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Externě viditelného členu obsahuje podpis, který obsahuje vnořený argument typu.

## <a name="rule-description"></a>Popis pravidla
 Vnořený typ argumentu je typ argumentu, který je také obecným typem. Chce-li uživatel zavolat člen, jehož předpis obsahuje vnořený argument typu, musí nejprve vytvořit instanci jednoho obecného typu a předat tento typ konstruktoru druhého obecného typu. Potřebná procedura a syntaxe je složitá a je vhodné se jí vyhnout.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, změňte návrh odebrat vnořený typ argumentu.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo. Poskytuje obecné typy v syntaxi, která je snadno pochopitelný a snižuje čas, který je potřeba další informace a zvýší frekvence přijetí nové knihovny.

## <a name="example"></a>Příklad
 Následující příklad ukazuje metodu, která porušuje pravidlo a syntaxi, která je potřeba volat metodu porušení.

 [!code-vb[FxCop.Design.NestedGenerics#1](../code-quality/codesnippet/VisualBasic/ca1006-do-not-nest-generic-types-in-member-signatures_1.vb)]
 [!code-csharp[FxCop.Design.NestedGenerics#1](../code-quality/codesnippet/CSharp/ca1006-do-not-nest-generic-types-in-member-signatures_1.cs)]

## <a name="related-rules"></a>Související pravidla
 [CA1005: Vyhněte se nadbytečným parametrům na obecných typech](../code-quality/ca1005-avoid-excessive-parameters-on-generic-types.md)

 [CA1010: Kolekce musí implementovat obecné rozhraní](../code-quality/ca1010-collections-should-implement-generic-interface.md)

 [CA1000: Nedeklarujte statické členy v obecných typech](../code-quality/ca1000-do-not-declare-static-members-on-generic-types.md)

 [CA1002: Nezveřejňujte obecné seznamy](../code-quality/ca1002-do-not-expose-generic-lists.md)

 [CA1004: Obecné metody by měly poskytnout parametr typu](../code-quality/ca1004-generic-methods-should-provide-type-parameter.md)

 [CA1003: Použijte instance obecných události obslužné rutiny](../code-quality/ca1003-use-generic-event-handler-instances.md)

 [CA1007: Použijte obecné typy, kde je to vhodné](../code-quality/ca1007-use-generics-where-appropriate.md)

## <a name="see-also"></a>Viz také:
 [Obecné typy](/dotnet/csharp/programming-guide/generics/index)