---
title: 'CA2241: Poskytněte správné argumenty metodě formátování | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2241
- Provide correct arguments to formatting methods
- ProvideCorrectArgumentsToFormattingMethods
helpviewer_keywords:
- ProvideCorrectArgumentsToFormattingMethods
- CA2241
ms.assetid: 83639bc4-4c91-4a07-a40e-dc5e49a84494
caps.latest.revision: 14
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 0a139db3fb1ece41c1d3f18471a286c72a7a576c
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68201515"
---
# <a name="ca2241-provide-correct-arguments-to-formatting-methods"></a>CA2241: Zadejte správné argumenty pro metody formátování
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|ProvideCorrectArgumentsToFormattingMethods|
|CheckId|CA2241|
|Kategorie|Microsoft.Usage|
|Narušující změna|Pevné|

## <a name="cause"></a>příčina
 `format` Řetězcový argument předaný metodě například <xref:System.Console.WriteLine%2A>, <xref:System.Console.Write%2A>, nebo <xref:System.String.Format%2A?displayProperty=fullName> neobsahuje položky formátu, který odpovídá každému argumentu objektu nebo naopak.

## <a name="rule-description"></a>Popis pravidla
 Argumenty pro metody jako <xref:System.Console.WriteLine%2A>, <xref:System.Console.Write%2A>, a <xref:System.String.Format%2A> obsahovat řetězec formátu, za nímž následuje několik <xref:System.Object?displayProperty=fullName> instancí. Řetězec formátu se skládá z textu a vložené formátu položek formuláře, {index [, zarovnání] [: formatString]}. "index" je založený na nule celého čísla, která označuje, které objekty, které chcete formátovat. Pokud objekt nemá odpovídající index ve formátovacím řetězci, objekt se ignoruje. Pokud objektu určeném "index" buď neexistuje, <xref:System.FormatException?displayProperty=fullName> je vyvolána výjimka za běhu.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, poskytují formát položky pro každý objekt argument a argument objektu pro každou položku formátu.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo.

## <a name="example"></a>Příklad
 Následující příklad ukazuje dva porušení tohoto pravidla.

 [!code-csharp[FxCop.Usage.FormattingArguments#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.FormattingArguments/cs/FxCop.Usage.FormattingArguments.cs#1)]
 [!code-vb[FxCop.Usage.FormattingArguments#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Usage.FormattingArguments/vb/FxCop.Usage.FormattingArguments.vb#1)]
