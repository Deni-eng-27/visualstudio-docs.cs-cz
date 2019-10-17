---
title: 'CA1023: Indexery by neměly být multidimenzionální'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IndexersShouldNotBeMultidimensional
- CA1023
helpviewer_keywords:
- CA1023
- IndexersShouldNotBeMultidimensional
ms.assetid: ae499879-97f6-434e-a61d-1fedd231d2fb
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 9b9488d3f28567e3e39f86355b353f6d1d9d84d9
ms.sourcegitcommit: 485ffaedb1ade71490f11cf05962add1718945cc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/16/2019
ms.locfileid: "72441422"
---
# <a name="ca1023-indexers-should-not-be-multidimensional"></a>CA1023: Indexery by neměly být multidimenzionální

|||
|-|-|
|TypeName|IndexersShouldNotBeMultidimensional|
|CheckId|CA1023|
|Kategorie|Microsoft. Design|
|Zásadní změna|Narušující|

## <a name="cause"></a>příčina
Veřejný nebo chráněný typ obsahuje veřejný nebo chráněný indexer, který používá více než jeden index.

## <a name="rule-description"></a>Popis pravidla
Indexery, tj. indexované vlastnosti, by měly používat jeden index. Multidimenzionální indexery můžou významně snížit použitelnost knihovny. Pokud návrh vyžaduje více indexů, je třeba znovu zvážit, zda typ představuje logické úložiště dat. V takovém případě použijte metodu.

## <a name="how-to-fix-violations"></a>Jak opravit porušení
Chcete-li opravit porušení tohoto pravidla, změňte návrh tak, aby používal celé číslo jedinou nebo index řetězce, nebo použijte metodu místo indexeru.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
Potlačí upozornění z tohoto pravidla až po pečlivém zvážení nutnosti nestandardního indexeru.

## <a name="example"></a>Příklad
Následující příklad ukazuje typ, `DayOfWeek03` s multidimenzionálním indexerem, který porušuje pravidlo. Indexer se může zobrazit jako typ převodu, a proto je lépe přístupný jako metoda. Typ je přepracován v `RedesignedDayOfWeek03` pro splnění pravidla.

[!code-vb[FxCop.Design.OneDimensionForIndexer#1](../code-quality/codesnippet/VisualBasic/ca1023-indexers-should-not-be-multidimensional_1.vb)]
[!code-cpp[FxCop.Design.OneDimensionForIndexer#1](../code-quality/codesnippet/CPP/ca1023-indexers-should-not-be-multidimensional_1.cpp)]
[!code-csharp[FxCop.Design.OneDimensionForIndexer#1](../code-quality/codesnippet/CSharp/ca1023-indexers-should-not-be-multidimensional_1.cs)]

## <a name="related-rules"></a>Související pravidla
[CA1043: Použijte celočíselný nebo řetězcový argument pro indexery](../code-quality/ca1043-use-integral-or-string-argument-for-indexers.md)

[CA1024: Použijte vlastnosti, kde je to vhodné](../code-quality/ca1024-use-properties-where-appropriate.md)
