---
title: 'CA1502: Vyhněte se nadměrné složitosti'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- AvoidExcessiveComplexity
- CA1502
helpviewer_keywords:
- CA1502
- AvoidExcessiveComplexity
ms.assetid: d735454b-2f8f-47ce-907d-f7a5a5391221
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 35fa770c9a7f1d2e0a5d1a5634edf21caae26cfc
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55006131"
---
# <a name="ca1502-avoid-excessive-complexity"></a>CA1502: Vyhněte se nadměrné složitosti

|||
|-|-|
|TypeName|AvoidExcessiveComplexity|
|CheckId|CA1502|
|Kategorie|Microsoft.Maintainability|
|Narušující změna|Nenarušující|

## <a name="cause"></a>Příčina

Metoda má nadměrnou cyklomatická složitost.

## <a name="rule-description"></a>Popis pravidla

*Cyklomatická složitost* měří počet lineárně nezávislých cest skrze metodu, která je určeno počtem a složitostí podmínkových větví. Nízká cyclomatickou složitost obecně označuje metodu, která je snadno pochopit, testování a udržovat. Cyklomatická složitost se počítá z ovládacího prvku grafu toku metody a dostane následujícím způsobem:

cyklomatická složitost = počtu hran – počet uzlů + 1

Pokud uzel představuje bod větve logiky a hraniční představuje čáry mezi uzly.

Pravidlo oznámí porušení cyklomatická složitost po více než 25.

Další informace o metriky kódu na [měření složitosti a udržovatelnosti spravovaného kódu](../code-quality/code-metrics-values.md),

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

Chcete-li opravit porušení tohoto pravidla, Refaktorujte metodu pro snížení jeho cyklomatická složitost.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Je bezpečné potlačit upozornění tohoto pravidla, pokud nelze snadno snižují složitost a metoda je snadno pochopit, testování a udržovat. Zejména metoda, která obsahuje velké `switch` (`Select` v [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]) příkaz je mezi kandidáty pro vyloučení. Riziko destabilizing základní pozdní v cyklu vývoje nebo zavedení nečekaným změnám v chování za běhu v dříve dodané kódu může pomocí převážit nad výhodami refaktorování kódu udržovatelnosti kódu.

## <a name="how-cyclomatic-complexity-is-calculated"></a>Jak se počítá Cyklomatická složitost

Cyklomatická složitost se vypočte tak, že přidáte 1 takto:

- Počet větví (například `if`, `while`, a `do`)

- Počet `case` příkazů v `switch`

## <a name="example"></a>Příklad

Následující příklady ukazují metody, které mají různou cyklomatické složitosti.

**Cyklomatická složitost 1**

[!code-cpp[FxCop.Maintainability.AvoidExcessiveComplexity#1](../code-quality/codesnippet/CPP/ca1502-avoid-excessive-complexity_1.cpp)]
[!code-vb[FxCop.Maintainability.AvoidExcessiveComplexity#1](../code-quality/codesnippet/VisualBasic/ca1502-avoid-excessive-complexity_1.vb)]
[!code-csharp[FxCop.Maintainability.AvoidExcessiveComplexity#1](../code-quality/codesnippet/CSharp/ca1502-avoid-excessive-complexity_1.cs)]

## <a name="example"></a>Příklad

**Cyklomatická složitost 2**

[!code-cpp[FxCop.Maintainability.AvoidExcessiveComplexity#2](../code-quality/codesnippet/CPP/ca1502-avoid-excessive-complexity_2.cpp)]
[!code-vb[FxCop.Maintainability.AvoidExcessiveComplexity#2](../code-quality/codesnippet/VisualBasic/ca1502-avoid-excessive-complexity_2.vb)]
[!code-csharp[FxCop.Maintainability.AvoidExcessiveComplexity#2](../code-quality/codesnippet/CSharp/ca1502-avoid-excessive-complexity_2.cs)]

## <a name="example"></a>Příklad

**Cyklomatická složitost 3**

[!code-cpp[FxCop.Maintainability.AvoidExcessiveComplexity#3](../code-quality/codesnippet/CPP/ca1502-avoid-excessive-complexity_3.cpp)]
[!code-vb[FxCop.Maintainability.AvoidExcessiveComplexity#3](../code-quality/codesnippet/VisualBasic/ca1502-avoid-excessive-complexity_3.vb)]
[!code-csharp[FxCop.Maintainability.AvoidExcessiveComplexity#3](../code-quality/codesnippet/CSharp/ca1502-avoid-excessive-complexity_3.cs)]

## <a name="example"></a>Příklad

**Cyklomatická složitost 8**

[!code-cpp[FxCop.Maintainability.AvoidExcessiveComplexity#4](../code-quality/codesnippet/CPP/ca1502-avoid-excessive-complexity_4.cpp)]
[!code-vb[FxCop.Maintainability.AvoidExcessiveComplexity#4](../code-quality/codesnippet/VisualBasic/ca1502-avoid-excessive-complexity_4.vb)]
[!code-csharp[FxCop.Maintainability.AvoidExcessiveComplexity#4](../code-quality/codesnippet/CSharp/ca1502-avoid-excessive-complexity_4.cs)]

## <a name="related-rules"></a>Související pravidla

[CA1501: Vyhněte se nadměrné dědičnosti](../code-quality/ca1501-avoid-excessive-inheritance.md)

## <a name="see-also"></a>Viz také:

- [Měření složitosti a udržovatelnosti spravovaného kódu](../code-quality/code-metrics-values.md)