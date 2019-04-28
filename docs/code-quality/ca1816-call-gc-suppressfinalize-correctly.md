---
title: 'CA1816: Volejte správně GC.SuppressFinalize'
ms.date: 06/30/2018
ms.topic: reference
f1_keywords:
- CA1816
- DisposeMethodsShouldCallSuppressFinalize
helpviewer_keywords:
- DisposeMethodsShouldCallSuppressFinalize
- CA1816
ms.assetid: 47915fbb-103f-4333-b157-1da16bf49660
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 2c14f9ed8803c02d1570ac2a3dee82fbdfca5f01
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62796777"
---
# <a name="ca1816-call-gcsuppressfinalize-correctly"></a>CA1816: Volejte správně GC.SuppressFinalize

|||
|-|-|
|TypeName|CallGCSuppressFinalizeCorrectly|
|CheckId|CA1816|
|Kategorie|Microsoft. Použití|
|Narušující změna|Pevné|

## <a name="cause"></a>Příčina

Porušení tohoto pravidla může být způsobeno:

- Metoda, která je implementací <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> a nevolá <xref:System.GC.SuppressFinalize%2A?displayProperty=nameWithType>.

- Metoda, která není implementací <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> a volání <xref:System.GC.SuppressFinalize%2A?displayProperty=nameWithType>.

- Metoda, která volá <xref:System.GC.SuppressFinalize%2A?displayProperty=nameWithType> a předává něco jiného než [tento (C#)](/dotnet/csharp/language-reference/keywords/this) nebo [Me (Visual Basic)](/dotnet/visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass#me).

## <a name="rule-description"></a>Popis pravidla

<xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> Metoda umožňuje uživatelům uvolnění prostředků kdykoli před objektu poté jsou dostupné pro uvolnění paměti. Pokud <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> metoda je volána, uvolnění prostředků objektu. Díky tomu finalizace zbytečné. <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> by měly volat <xref:System.GC.SuppressFinalize%2A?displayProperty=nameWithType> tak systému uvolňování paměti nebude volat finalizační metodu objektu.

Chcete-li zabránit odvozené typy s finalizační metody by bylo nutné znovu implementovat <xref:System.IDisposable> a pro její zavolání, měla by volat stále nezapečetěné typy bez finalizačních metod <xref:System.GC.SuppressFinalize%2A?displayProperty=nameWithType>.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

Chcete-li opravit porušení tohoto pravidla:

- Pokud metoda je implementací <xref:System.IDisposable.Dispose%2A>, přidejte volání do <xref:System.GC.SuppressFinalize%2A?displayProperty=nameWithType>.

- Pokud metoda není implementace <xref:System.IDisposable.Dispose%2A>, buď odeberte volání <xref:System.GC.SuppressFinalize%2A?displayProperty=nameWithType> nebo ji přesunout do tohoto typu <xref:System.IDisposable.Dispose%2A> implementace.

- Změna všechna volání <xref:System.GC.SuppressFinalize%2A?displayProperty=nameWithType> předat [tento (C#)](/dotnet/csharp/language-reference/keywords/this) nebo [Me (Visual Basic)](/dotnet/visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass#me).

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Pouze potlačit upozornění tohoto pravidla, pokud úmyslně použijete <xref:System.GC.SuppressFinalize%2A?displayProperty=nameWithType> řídit dobu života jiné objekty. Pokud implementace není potlačit upozornění tohoto pravidla <xref:System.IDisposable.Dispose%2A> nevolá <xref:System.GC.SuppressFinalize%2A?displayProperty=nameWithType>. V takovém případě služeb při selhání pro potlačení dokončení snižuje výkon a poskytuje žádné výhody.

## <a name="example-that-violates-ca1816"></a>Příklad, který je v rozporu CA1816

Tento kód ukazuje metodu, která volá <xref:System.GC.SuppressFinalize%2A?displayProperty=nameWithType>, ale není úspěšný [tento (C#)](/dotnet/csharp/language-reference/keywords/this) nebo [Me (Visual Basic)](/dotnet/visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass#me). Tento kód v důsledku toho porušuje pravidlo CA1816.

[!code-vb[FxCop.Usage.CallGCSuppressFinalizeCorrectly#1](../code-quality/codesnippet/VisualBasic/ca1816-call-gc-suppressfinalize-correctly_1.vb)]
[!code-csharp[FxCop.Usage.CallGCSuppressFinalizeCorrectly#1](../code-quality/codesnippet/CSharp/ca1816-call-gc-suppressfinalize-correctly_1.cs)]

## <a name="example-that-satisfies-ca1816"></a>Příklad, který splňuje CA1816

Tento příklad ukazuje metodu, která správně volá <xref:System.GC.SuppressFinalize%2A?displayProperty=nameWithType> předáním [tento (C#)](/dotnet/csharp/language-reference/keywords/this) nebo [Me (Visual Basic)](/dotnet/visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass#me).

[!code-vb[FxCop.Usage.CallGCSuppressFinalizeCorrectly2#1](../code-quality/codesnippet/VisualBasic/ca1816-call-gc-suppressfinalize-correctly_2.vb)]
[!code-csharp[FxCop.Usage.CallGCSuppressFinalizeCorrectly2#1](../code-quality/codesnippet/CSharp/ca1816-call-gc-suppressfinalize-correctly_2.cs)]

## <a name="related-rules"></a>Související pravidla

- [CA2215: Metody Dispose by měly volat uvolnění třídy base](../code-quality/ca2215-dispose-methods-should-call-base-class-dispose.md)
- [CA2216: Uvolnitelné typy by měly deklarovat finalizační metodu](../code-quality/ca2216-disposable-types-should-declare-finalizer.md)

## <a name="see-also"></a>Viz také:

- [Vzor dispose](/dotnet/standard/design-guidelines/dispose-pattern)