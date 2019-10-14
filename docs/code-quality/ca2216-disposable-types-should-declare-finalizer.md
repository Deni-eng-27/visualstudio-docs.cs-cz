---
title: 'CA2216: Uvolnitelné typy by měly deklarovat finalizační metodu'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- DisposableTypesShouldDeclareFinalizer
- CA2216
helpviewer_keywords:
- CA2216
- DisposableTypesShouldDeclareFinalizer
ms.assetid: 0cabcc5e-b526-452b-8c2a-0cbe3b93c0ef
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 3ac52bdb17aeb7d04e434d2b02ff9a905eab49a2
ms.sourcegitcommit: 034c503ae04e22cf840ccb9770bffd012e40fb2d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/14/2019
ms.locfileid: "72305925"
---
# <a name="ca2216-disposable-types-should-declare-finalizer"></a>CA2216: Uvolnitelné typy by měly deklarovat finalizační metodu

|||
|-|-|
|TypeName|DisposableTypesShouldDeclareFinalizer|
|CheckId|CA2216|
|Category|Microsoft.Usage|
|Zásadní změna|Nenarušující|

## <a name="cause"></a>Příčina

Typ, který implementuje <xref:System.IDisposable?displayProperty=fullName> a obsahuje pole, která navrhují použití nespravovaných prostředků, neimplementuje finalizační metodu, jak je popsáno v <xref:System.Object.Finalize%2A?displayProperty=fullName>.

## <a name="rule-description"></a>Popis pravidla

Porušení tohoto pravidla je hlášeno, pokud typ mimo použití obsahuje pole následujících typů:

- <xref:System.IntPtr?displayProperty=fullName>

- <xref:System.UIntPtr?displayProperty=fullName>

- <xref:System.Runtime.InteropServices.HandleRef?displayProperty=fullName>

## <a name="how-to-fix-violations"></a>Jak opravit porušení

Chcete-li opravit porušení tohoto pravidla, implementujte finalizační metodu, která volá vaši metodu <xref:System.IDisposable.Dispose%2A>.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Je bezpečné potlačit upozornění od tohoto pravidla, pokud typ neimplementuje <xref:System.IDisposable> pro účely uvolňování nespravovaných prostředků.

## <a name="example"></a>Příklad

Následující příklad ukazuje typ, který je v rozporu s tímto pravidlem.

[!code-csharp[FxCop.Usage.DisposeNoFinalize#1](../code-quality/codesnippet/CSharp/ca2216-disposable-types-should-declare-finalizer_1.cs)]

## <a name="related-rules"></a>Související pravidla

[CA2115: Vyvolejte GC. Udržení naživu při použití nativních prostředků @ no__t-0

[CA1816: Vyvolejte GC. SuppressFinalize správně @ no__t-0

[CA1049: Typy, které vlastní nativní prostředky by měly být na jedno použití @ no__t-0

## <a name="see-also"></a>Viz také:

- <xref:System.IDisposable?displayProperty=fullName>
- <xref:System.IntPtr?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.HandleRef?displayProperty=fullName>
- <xref:System.UIntPtr?displayProperty=fullName>
- <xref:System.Object.Finalize%2A?displayProperty=fullName>
- [Vzor pro metodu Dispose](/dotnet/standard/design-guidelines/dispose-pattern)