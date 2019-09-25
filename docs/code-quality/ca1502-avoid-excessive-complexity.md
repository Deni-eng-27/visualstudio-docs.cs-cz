---
title: 'CA1502: Vyhněte se nadměrné složitosti'
ms.date: 11/04/2016
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
ms.openlocfilehash: db4f767aa2ecb31bca3a5530e1b4bbf5ce15729d
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/24/2019
ms.locfileid: "71234550"
---
# <a name="ca1502-avoid-excessive-complexity"></a>CA1502: Vyhněte se nadměrné složitosti

|||
|-|-|
|TypeName|AvoidExcessiveComplexity|
|CheckId|CA1502|
|Kategorie|Microsoft. udržovatelnost|
|Zásadní změna|Nenarušující|

## <a name="cause"></a>příčina

Metoda má nadměrně Cyklomatická složitost.

## <a name="rule-description"></a>Popis pravidla

*Cyklomatická složitost* měří počet lineárně nezávislých cest pomocí metody, která je určena počtem a složitostí podmíněných větví. Nízká složitost cyklomatická obecně označuje metodu, která je snadno srozumitelná, testovat a udržovatelná. Složitá cyklomatická je počítána z grafu toku ovládacích prvků metody a je dána následujícím způsobem:

Cyklomatická složitost = počet okrajů – počet uzlů + 1

*Uzel* představuje bod logické větve a *hrana* představuje spojnici mezi uzly.

Pravidlo nahlásí porušení, pokud je Cyklomatická složitost větší než 25.

Můžete získat další informace o metrikách kódu při [Měření složitosti spravovaného kódu](../code-quality/code-metrics-values.md).

## <a name="how-to-fix-violations"></a>Jak opravit porušení

Chcete-li opravit porušení tohoto pravidla, refaktorujte metodu pro snížení složitosti cyklomatická.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Z tohoto pravidla je bezpečné potlačit upozornění, pokud složitost nelze snadno snížit a metodu je snadné pochopit, otestovat a udržovat. Konkrétně metoda, která obsahuje velký `switch` (`Select` v [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]) příkaz, je kandidátem pro vyloučení. Riziko, že destabilizující základ kódu v cyklu vývoje nebo Představujeme neočekávanou změnu v chování za běhu v dříve dodaném kódu, může mít za následek převážení výhod udržovatelnosti refaktoringu kódu.

## <a name="how-cyclomatic-complexity-is-calculated"></a>Jak se počítá složitost cyklomatická

Složitost cyklomatická se počítá přidáním 1 k následujícím akcím:

- Počet větví (například `if`, `while`a `do`)

- `case` Počet příkazů v`switch`

## <a name="example"></a>Příklad

Následující příklady znázorňují metody, které mají různé cyklomatická složité.

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