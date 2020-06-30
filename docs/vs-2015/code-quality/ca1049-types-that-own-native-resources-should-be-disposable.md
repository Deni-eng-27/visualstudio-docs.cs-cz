---
title: 'CA1049: typy, které vlastní nativní prostředky by měly být na jedno použití | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1049
- TypesThatOwnNativeResourcesShouldBeDisposable
helpviewer_keywords:
- TypesThatOwnNativeResourcesShouldBeDisposable
- CA1049
ms.assetid: 084e587d-0e45-4092-b767-49eed30d6a35
caps.latest.revision: 19
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 49c56b98e3be01675c2c21cd11c2961dd75f4877
ms.sourcegitcommit: b885f26e015d03eafe7c885040644a52bb071fae
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/30/2020
ms.locfileid: "85546806"
---
# <a name="ca1049-types-that-own-native-resources-should-be-disposable"></a>CA1049: Typy, které vlastní nativní prostředky, by měly být uvolnitelné
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|Položka|Hodnota|
|-|-|
|TypeName|TypesThatOwnNativeResourcesShouldBeDisposable|
|CheckId|CA1049|
|Kategorie|Microsoft. Design|
|Narušující změna|Nenarušující|

## <a name="cause"></a>Příčina
 Typ odkazuje na <xref:System.IntPtr?displayProperty=fullName> pole, <xref:System.UIntPtr?displayProperty=fullName> pole nebo <xref:System.Runtime.InteropServices.HandleRef?displayProperty=fullName> pole, ale neimplementuje <xref:System.IDisposable?displayProperty=fullName> .

## <a name="rule-description"></a>Popis pravidla
 Toto pravidlo předpokládá, že <xref:System.IntPtr> , <xref:System.UIntPtr> a <xref:System.Runtime.InteropServices.HandleRef> pole ukládají ukazatele do nespravovaných prostředků. Typy, které přidělují nespravované prostředky, by měly implementovat, <xref:System.IDisposable> aby volajícím uvolnili tyto prostředky na vyžádání a zkrátili životnost objektů, které uchovávají prostředky.

 Doporučený návrhový vzor pro vyčištění nespravovaných prostředků je poskytnout implicitní a explicitní způsob, jak uvolnit tyto prostředky pomocí <xref:System.Object.Finalize%2A?displayProperty=fullName> metody a <xref:System.IDisposable.Dispose%2A?displayProperty=fullName> metody, v uvedeném pořadí. Systém uvolňování paměti volá <xref:System.Object.Finalize%2A> metodu objektu v neurčitém čase po zjištění, že je objekt již dostupný. Po <xref:System.Object.Finalize%2A> volání je vyžadován další uvolňování paměti pro uvolnění objektu. <xref:System.IDisposable.Dispose%2A>Metoda umožňuje volajícímu explicitně uvolnit prostředky na vyžádání, a to dříve, než budou prostředky uvolněny, pokud zbývá do uvolňování paměti. Po vyčištění nespravovaných prostředků <xref:System.IDisposable.Dispose%2A> by měla zavolat <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName> metodu, aby systém uvolňování paměti věděl, že již není nutné <xref:System.Object.Finalize%2A> volat, což eliminuje nutnost dalšího uvolňování paměti a zkrátí životnost objektu.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, implementujte <xref:System.IDisposable> .

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Pokud typ neodkazuje na nespravovaný prostředek, je bezpečné potlačit upozornění od tohoto pravidla. V opačném případě potlačí upozornění z tohoto pravidla, protože selhání implementace <xref:System.IDisposable> může způsobit nedostupnost nespravovaných prostředků nebo nepoužívané.

## <a name="example"></a>Příklad
 Následující příklad ukazuje typ, který implementuje <xref:System.IDisposable> k vyčištění nespravovaného prostředku.

 [!code-csharp[FxCop.Design.UnmanagedResources#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.UnmanagedResources/cs/FxCop.Design.UnmanagedResources.cs#1)]
 [!code-vb[FxCop.Design.UnmanagedResources#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.UnmanagedResources/vb/FxCop.Design.UnmanagedResources.vb#1)]

## <a name="related-rules"></a>Související pravidla
 [CA2115: Volejte GC.KeepAlive při použití nativních prostředků](../code-quality/ca2115-call-gc-keepalive-when-using-native-resources.md)

 [CA1816: Volejte správně GC.SuppressFinalize](../code-quality/ca1816-call-gc-suppressfinalize-correctly.md)

 [CA2216: Uvolnitelné typy by měly deklarovat finalizační metodu](../code-quality/ca2216-disposable-types-should-declare-finalizer.md)

 [CA1001: Typy, které vlastní uvolnitelné pole, by měly být uvolnitelné](../code-quality/ca1001-types-that-own-disposable-fields-should-be-disposable.md)

## <a name="see-also"></a>Viz také
  [Vzor pro metodu Dispose](https://msdn.microsoft.com/library/31a6c13b-d6a2-492b-9a9f-e5238c983bcb)
