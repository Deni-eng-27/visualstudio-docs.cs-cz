---
title: 'CA1001: typy, které vlastní pole na jedno použití, by měly být samostatně | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1001
- TypesThatOwnDisposableFieldsShouldBeDisposable
helpviewer_keywords:
- CA1001
- TypesThatOwnDisposableFieldsShouldBeDisposable
ms.assetid: c85c126c-2b16-4505-940a-b5ddf873fb22
caps.latest.revision: 23
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: dab4532f082bd81eaa7b812eb038c5957636d453
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "85548314"
---
# <a name="ca1001-types-that-own-disposable-fields-should-be-disposable"></a>CA1001: Typy, které vlastní uvolnitelné pole, by měly být uvolnitelné
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|Položka|Hodnota|
|-|-|
|TypeName|TypesThatOwnDisposableFieldsShouldBeDisposable|
|CheckId|CA1001|
|Kategorie|Microsoft. Design|
|Narušující změna|Bez přerušení – Pokud typ není viditelný vně sestavení.<br /><br /> Přerušení – Pokud je typ viditelný mimo sestavení.|

## <a name="cause"></a>Příčina
 Třída deklaruje a implementuje pole instance, které je <xref:System.IDisposable?displayProperty=fullName> typu a třída neimplementuje <xref:System.IDisposable> .

## <a name="rule-description"></a>Popis pravidla
 Třída implementuje <xref:System.IDisposable> rozhraní pro uvolnění nespravovaných prostředků, které vlastní. Pole instance, které je <xref:System.IDisposable> typu, označuje, že pole vlastní nespravovaný prostředek. Třída, která deklaruje <xref:System.IDisposable> pole nepřímo vlastní nespravovaný prostředek a měla by implementovat <xref:System.IDisposable> rozhraní. Pokud třída přímo nevlastní žádné nespravované prostředky, neměli byste implementovat finalizační metodu.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, implementujte <xref:System.IDisposable> a z <xref:System.IDisposable.Dispose%2A?displayProperty=fullName> metody zavolejte <xref:System.IDisposable.Dispose%2A> metodu pole.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo.

## <a name="example"></a>Příklad
 Následující příklad ukazuje třídu, která porušuje pravidlo a třídu, která splňuje pravidlo implementací <xref:System.IDisposable> . Třída neimplementuje finalizační metodu, protože třída přímo nevlastní žádné nespravované prostředky.

 [!code-csharp[FxCop.Design.DisposableFields#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.DisposableFields/cs/FxCop.Design.DisposableFields.cs#1)]
 [!code-vb[FxCop.Design.DisposableFields#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.DisposableFields/vb/FxCop.Design.DisposableFields.vb#1)]

## <a name="related-rules"></a>Související pravidla
 [CA2213: Uvolnitelná pole by měla být uvolněna](../code-quality/ca2213-disposable-fields-should-be-disposed.md)

 [CA2216: Uvolnitelné typy by měly deklarovat finalizační metodu](../code-quality/ca2216-disposable-types-should-declare-finalizer.md)

 [CA2215: Metody Dispose by měly volat uvolnění základní třídy](../code-quality/ca2215-dispose-methods-should-call-base-class-dispose.md)

 [CA1049: Typy, které vlastní nativní prostředky, by měly být uvolnitelné](../code-quality/ca1049-types-that-own-native-resources-should-be-disposable.md)
