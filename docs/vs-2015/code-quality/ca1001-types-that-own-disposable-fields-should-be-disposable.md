---
title: 'CA1001: Typy, které vlastní uvolnitelné pole by měly být uvolnitelné | Dokumentace Microsoftu'
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
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 98be3bafb582e4d48560108625be911e53acf664
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62562312"
---
# <a name="ca1001-types-that-own-disposable-fields-should-be-disposable"></a>CA1001: Typy, které vlastní uvolnitelné pole, by měly být uvolnitelné
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|TypesThatOwnDisposableFieldsShouldBeDisposable|  
|CheckId|CA1001|  
|Kategorie|Microsoft.Design|  
|Narušující změna|Bez konce – Pokud typ není viditelný mimo sestavení.<br /><br /> Rozdělení – typ je viditelný mimo sestavení.|  
  
## <a name="cause"></a>Příčina  
 Třída deklaruje a implementuje pole instance, která je <xref:System.IDisposable?displayProperty=fullName> typ a třída neimplementuje <xref:System.IDisposable>.  
  
## <a name="rule-description"></a>Popis pravidla  
 Třída implementuje <xref:System.IDisposable> rozhraní k uvolnění nespravovaných prostředků, které vlastní. Pole instance, která je <xref:System.IDisposable> označuje, že pole vlastní nespravovaný zdroj. Třída, která deklaruje <xref:System.IDisposable> pole nepřímo vlastní nespravovaný zdroj a měla by implementovat <xref:System.IDisposable> rozhraní. Pokud třída není přímo vlastníkem jakýchkoliv nespravovaných prostředků, neměly by implementovat finalizační metodu.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení tohoto pravidla, implementovat <xref:System.IDisposable> z a <xref:System.IDisposable.Dispose%2A?displayProperty=fullName> volání metody <xref:System.IDisposable.Dispose%2A> metoda pole.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění na toto pravidlo.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje třídu, která porušuje pravidlo a třídy, která splňuje pravidlo implementací <xref:System.IDisposable>. Třída neimplementuje finalizační metodu, protože třída není přímo vlastníkem jakýchkoliv nespravovaných prostředků.  
  
 [!code-csharp[FxCop.Design.DisposableFields#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.DisposableFields/cs/FxCop.Design.DisposableFields.cs#1)]
 [!code-vb[FxCop.Design.DisposableFields#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.DisposableFields/vb/FxCop.Design.DisposableFields.vb#1)]  
  
## <a name="related-rules"></a>Související pravidla  
 [CA2213: Uvolnitelné pole by mělo být uvolněno](../code-quality/ca2213-disposable-fields-should-be-disposed.md)  
  
 [CA2216: Uvolnitelné typy by měly deklarovat finalizační metodu](../code-quality/ca2216-disposable-types-should-declare-finalizer.md)  
  
 [CA2215: Metody Dispose by měly volat uvolnění třídy base](../code-quality/ca2215-dispose-methods-should-call-base-class-dispose.md)  
  
 [CA1049: Typy, které vlastní nativní prostředky by měly být uvolnitelné](../code-quality/ca1049-types-that-own-native-resources-should-be-disposable.md)
