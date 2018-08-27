---
title: 'CA1023: Indexery by neměly být multidimenzionální | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IndexersShouldNotBeMultidimensional
- CA1023
helpviewer_keywords:
- CA1023
- IndexersShouldNotBeMultidimensional
ms.assetid: ae499879-97f6-434e-a61d-1fedd231d2fb
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: e1b1022484db26e6ff8fbc0046333f187753bb53
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/24/2018
ms.locfileid: "42901230"
---
# <a name="ca1023-indexers-should-not-be-multidimensional"></a>CA1023: Indexery by neměly být multidimenzionální
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CA1023: indexery by neměly být multidimenzionální](https://docs.microsoft.com/visualstudio/code-quality/ca1023-indexers-should-not-be-multidimensional).

|||
|-|-|
|TypeName|IndexersShouldNotBeMultidimensional|
|CheckId|CA1023|
|Kategorie|Microsoft.Design|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Veřejný nebo chráněný typ obsahuje veřejná nebo chráněná indexer, který používá více než jeden index.

## <a name="rule-description"></a>Popis pravidla
 Indexery, tj. indexované vlastnosti, by měly používat jediný index. Vícerozměrné indexery mohou výrazně snížit použitelnost knihovny. Pokud návrhu vyžaduje více indexů, zvažte, zda typ představuje logické datové úložiště. Pokud ne, použijte metodu.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, změňte návrhu a použít jedinou celé číslo nebo řetězec indexu nebo použijte metodu místo indexeru.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Potlačit upozornění tohoto pravidla až po pečlivého zvážení potřebu nestandardní indexeru.

## <a name="example"></a>Příklad
 Následující příklad ukazuje typ, `DayOfWeek03`, pomocí multidimenzionální indexeru, který porušuje pravidla. Indexer se dají považovat za typ převodu a proto je více správně vystavena jako metoda. Typ je upraveno `RedesignedDayOfWeek03` splňovat pravidla.

 [!code-cpp[FxCop.Design.OneDimensionForIndexer#1](../snippets/cpp/VS_Snippets_CodeAnalysis/FxCop.Design.OneDimensionForIndexer/cpp/FxCop.Design.OneDimensionForIndexer.cpp#1)]
 [!code-csharp[FxCop.Design.OneDimensionForIndexer#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.OneDimensionForIndexer/cs/FxCop.Design.OneDimensionForIndexer.cs#1)]
 [!code-vb[FxCop.Design.OneDimensionForIndexer#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.OneDimensionForIndexer/vb/FxCop.Design.OneDimensionForIndexer.vb#1)]

## <a name="related-rules"></a>Související pravidla
 [CA1043: Použijte celočíselný nebo řetězcový argument pro indexery](../code-quality/ca1043-use-integral-or-string-argument-for-indexers.md)

 [CA1024: Použijte vlastnosti, kde je to vhodné](../code-quality/ca1024-use-properties-where-appropriate.md)



