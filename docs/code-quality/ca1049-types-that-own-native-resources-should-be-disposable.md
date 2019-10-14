---
title: 'CA1049: Typy, které vlastní nativní prostředky, by měly být uvolnitelné'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1049
- TypesThatOwnNativeResourcesShouldBeDisposable
helpviewer_keywords:
- TypesThatOwnNativeResourcesShouldBeDisposable
- CA1049
ms.assetid: 084e587d-0e45-4092-b767-49eed30d6a35
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- cplusplus
ms.openlocfilehash: 03b8d222fc2349022ef324c9905279677fc86849
ms.sourcegitcommit: 034c503ae04e22cf840ccb9770bffd012e40fb2d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/14/2019
ms.locfileid: "72306114"
---
# <a name="ca1049-types-that-own-native-resources-should-be-disposable"></a>CA1049: Typy, které vlastní nativní prostředky, by měly být uvolnitelné

|||
|-|-|
|TypeName|TypesThatOwnNativeResourcesShouldBeDisposable|
|CheckId|CA1049|
|Category|Microsoft.Design|
|Zásadní změna|Nenarušující|

## <a name="cause"></a>Příčina

Typ odkazuje na pole <xref:System.IntPtr?displayProperty=fullName>, pole <xref:System.UIntPtr?displayProperty=fullName> nebo pole <xref:System.Runtime.InteropServices.HandleRef?displayProperty=fullName>, ale neimplementuje <xref:System.IDisposable?displayProperty=fullName>.

## <a name="rule-description"></a>Popis pravidla

Toto pravidlo předpokládá, že pole <xref:System.IntPtr>, <xref:System.UIntPtr> a <xref:System.Runtime.InteropServices.HandleRef> ukládají ukazatele na nespravované prostředky. Typy, které přidělují nespravované prostředky, by měly implementovat <xref:System.IDisposable>, aby volající mohli tyto prostředky uvolnit na vyžádání a zkrátit životnost objektů, které uchovávají prostředky.

Doporučený návrhový vzor pro vyčištění nespravovaných prostředků je poskytnout implicitní a explicitní způsob, jak uvolnit tyto prostředky pomocí metody <xref:System.Object.Finalize%2A?displayProperty=fullName> a metody <xref:System.IDisposable.Dispose%2A?displayProperty=fullName> v uvedeném pořadí. Systém uvolňování paměti volá metodu <xref:System.Object.Finalize%2A> objektu v neurčitém čase po zjištění, že je objekt již nedostupný. Po volání <xref:System.Object.Finalize%2A> je vyžadován další uvolňování paměti pro uvolnění objektu. Metoda <xref:System.IDisposable.Dispose%2A> umožňuje volajícímu explicitně uvolnit prostředky na vyžádání, a to dříve, než budou prostředky uvolněny, pokud zbývá do systému uvolňování paměti. Po vyčištění nespravovaných prostředků by <xref:System.IDisposable.Dispose%2A> volat metodu <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName>, aby systém uvolňování paměti mohl zjistit, že <xref:System.Object.Finalize%2A> již není nutné volat; Tím se eliminuje nutnost dalšího uvolňování paměti a zkrátí životnost objektu.

## <a name="how-to-fix-violations"></a>Jak opravit porušení
Chcete-li opravit porušení tohoto pravidla, implementujte <xref:System.IDisposable>.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
Pokud typ neodkazuje na nespravovaný prostředek, je bezpečné potlačit upozornění od tohoto pravidla. V opačném případě nedoporučujeme potlačit upozornění z tohoto pravidla, protože selhání implementace <xref:System.IDisposable> může způsobit, že nespravované prostředky nebudou dostupné nebo nepoužívané.

## <a name="example"></a>Příklad
Následující příklad ukazuje typ, který implementuje <xref:System.IDisposable> pro vyčištění nespravovaného prostředku.

[!code-csharp[FxCop.Design.UnmanagedResources#1](../code-quality/codesnippet/CSharp/ca1049-types-that-own-native-resources-should-be-disposable_1.cs)]
[!code-vb[FxCop.Design.UnmanagedResources#1](../code-quality/codesnippet/VisualBasic/ca1049-types-that-own-native-resources-should-be-disposable_1.vb)]

## <a name="related-rules"></a>Související pravidla
[CA2115: Vyvolejte GC. Udržení naživu při použití nativních prostředků @ no__t-0

[CA1816: Vyvolejte GC. SuppressFinalize správně @ no__t-0

[CA2216: Typy na jedno použití by měly deklarovat finalizační metodu @ no__t-0.

[CA1001: Typy, které vlastní pole na jedno použití, by měly být na jedno použití @ no__t-0

## <a name="see-also"></a>Viz také:

- [Vymazání nespravovaných prostředků](/dotnet/standard/garbage-collection/unmanaged)
- [Vzor pro metodu Dispose](/dotnet/standard/design-guidelines/dispose-pattern)