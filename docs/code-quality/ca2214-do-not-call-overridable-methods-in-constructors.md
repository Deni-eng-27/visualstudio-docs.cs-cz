---
title: 'CA2214: Nevolejte přepisovatelné metody v konstruktorech'
ms.date: 05/29/2016
ms.topic: reference
f1_keywords:
- DoNotCallOverridableMethodsInConstructors
- CA2214
helpviewer_keywords:
- CA2214
- DoNotCallOverridableMethodsInConstructors
ms.assetid: 335b57ca-a6e8-41b4-a20e-57ee172c97c3
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: a59346cb70269d4d2b405279fc9ea5573a879b1e
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/16/2019
ms.locfileid: "69546995"
---
# <a name="ca2214-do-not-call-overridable-methods-in-constructors"></a>CA2214: Nevolejte přepisovatelné metody v konstruktorech

|||
|-|-|
|TypeName|DoNotCallOverridableMethodsInConstructors|
|CheckId|CA2214|
|Kategorie|Microsoft.Usage|
|Narušující změna|Bez přerušení|

## <a name="cause"></a>příčina

Konstruktor nezapečetěného typu volá virtuální metodu definovanou ve své třídě.

## <a name="rule-description"></a>Popis pravidla

Při volání virtuální metody není skutečný typ, který spouští metodu, vybrán do doby běhu. Když konstruktor volá virtuální metodu, je možné, že konstruktor instance, která volá metodu, není proveden.

> [!NOTE]
> Starší verze analýzy tohoto pravidla obsahuje jinou diagnostickou zprávu " **\[název konstruktoru] obsahuje řetězec volání, jehož výsledkem je volání virtuální metody definované třídou. Přečtěte si následující zásobník volání pro nezamýšlené**následky. Implementace [FxCop analyzátorů](install-fxcop-analyzers.md) tohoto pravidla obsahuje diagnostickou zprávu "nevolat přepisovatelných**metod v konstruktorech**".

## <a name="how-to-fix-violations"></a>Jak opravit porušení

Chcete-li opravit porušení tohoto pravidla, Nevolejte virtuální metody typu v rámci konstruktorů typu.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Nepotlačujte upozornění na toto pravidlo. Konstruktor by měl být přepracován, aby se vyloučilo volání virtuální metody.

## <a name="example"></a>Příklad

Následující příklad ukazuje účinek porušení tohoto pravidla. Testovací aplikace vytvoří instanci `DerivedType`, která způsobí spuštění konstruktoru základní třídy (`BadlyConstructedType`). `BadlyConstructedType`konstruktor nesprávně volá virtuální metodu `DoSomething`. Jak výstup ukazuje, provede `DerivedType.DoSomething()` se před `DerivedType`spuštěním konstruktoru.

[!code-csharp[FxCop.Usage.CtorVirtual#1](../code-quality/codesnippet/CSharp/ca2214-do-not-call-overridable-methods-in-constructors_1.cs)]
[!code-vb[FxCop.Usage.CtorVirtual#1](../code-quality/codesnippet/VisualBasic/ca2214-do-not-call-overridable-methods-in-constructors_1.vb)]

Tento příklad vytvoří následující výstup:

```txt
Calling base ctor.
Derived DoSomething is called - initialized ? No
Calling derived ctor.
```