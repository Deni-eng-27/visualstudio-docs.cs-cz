---
title: 'CA1814: Upřednostněte vícenásobná pole před multidimenzionálními'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- PreferJaggedArraysOverMultidimensional
- CA1814
helpviewer_keywords:
- PreferJaggedArraysOverMultidimensional
- CA1814
ms.assetid: b1ccf563-2ec8-42e5-b89c-731a9de1ea1d
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: e2c7e7efe348526661b9de74b3631e6795608b99
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68921349"
---
# <a name="ca1814-prefer-jagged-arrays-over-multidimensional"></a>CA1814: Upřednostněte vícenásobná pole před multidimenzionálními

|||
|-|-|
|TypeName|PreferJaggedArraysOverMultidimensional|
|CheckId|CA1814|
|Kategorie|Microsoft. Performance|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
Člen je deklarován jako multidimenzionální pole.

## <a name="rule-description"></a>Popis pravidla
Vícenásobné pole je pole, jehož prvky jsou pole. Pole tvořící prvky mohou být různě velká, což vede k menšímu nevyužitému místu u některých sad dat.

## <a name="how-to-fix-violations"></a>Jak opravit porušení
Chcete-li opravit porušení tohoto pravidla, změňte multidimenzionální pole na vícenásobné pole.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
Potlačí upozornění z tohoto pravidla, pokud multidimenzionální pole nezahrnuje prostor.

## <a name="example"></a>Příklad
Následující příklad ukazuje deklarace pro zubatá a multidimenzionální pole.

[!code-vb[FxCop.Performance.JaggedArrays#1](../code-quality/codesnippet/VisualBasic/ca1814-prefer-jagged-arrays-over-multidimensional_1.vb)]
[!code-csharp[FxCop.Performance.JaggedArrays#1](../code-quality/codesnippet/CSharp/ca1814-prefer-jagged-arrays-over-multidimensional_1.cs)]