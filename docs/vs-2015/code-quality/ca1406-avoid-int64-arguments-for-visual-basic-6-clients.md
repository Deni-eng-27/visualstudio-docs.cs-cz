---
title: 'CA1406: Vyhněte se argumentům Int64 pro klienty jazyka Visual Basic 6 | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- AvoidInt64ArgumentsForVB6Clients
- CA1406
helpviewer_keywords:
- AvoidInt64ArgumentsForVB6Clients
- CA1406
ms.assetid: d5d0d3fc-f105-43da-be5b-923ab023309c
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 5947ce0bbcb19058cb32950e1e77cb3566b2ad2e
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/24/2018
ms.locfileid: "42902406"
---
# <a name="ca1406-avoid-int64-arguments-for-visual-basic-6-clients"></a>CA1406: Vyhněte se argumentům Int64 pro klienty jazyka Visual Basic 6
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CA1406: Vyhněte se Int64 argumenty pro klienty jazyka Visual Basic 6](https://docs.microsoft.com/visualstudio/code-quality/ca1406-avoid-int64-arguments-for-visual-basic-6-clients).

|||
|-|-|
|TypeName|AvoidInt64ArgumentsForVB6Clients|
|CheckId|CA1406|
|Kategorie|Microsoft.Interoperability|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Typ, který je označen jako viditelný pro Model COM (Component Object) deklaruje člen, že přejdete <xref:System.Int64?displayProperty=fullName> argument.

## <a name="rule-description"></a>Popis pravidla
 Klienty modulu COM jazyka Visual Basic 6 nemohou přistupovat k 64bitová celá čísla.

 Ve výchozím nastavení, jsou následující viditelné modelu COM: sestavení, veřejné typy, členy veřejné instance ve veřejných typů a členů veřejných hodnotových typech. Ale snížil počet falešných poplachů, toto pravidlo vyžaduje typ, který má být explicitně uvedena; viditelnost modelu COM musí být označené obsahující sestavení <xref:System.Runtime.InteropServices.ComVisibleAttribute?displayProperty=fullName> nastavena na `false` a typ musí být označeny pomocí <xref:System.Runtime.InteropServices.ComVisibleAttribute> nastavena na `true`.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla pro parametr, jehož hodnota může být vždy vyjádřený jako 32-bit integral, změňte typ parametru na <xref:System.Int32?displayProperty=fullName>. Pokud hodnota parametru může být větší, než může být vyjádřený jako 32-bit integral, změňte typ parametru na <xref:System.Decimal?displayProperty=fullName>. Všimněte si, že oba <xref:System.Single?displayProperty=fullName> a <xref:System.Double?displayProperty=fullName> ztratit přesnost na horní Rozsahy <xref:System.Int64> datového typu. Pokud se člen neměl být viditelné modelu COM, označte ji pomocí <xref:System.Runtime.InteropServices.ComVisibleAttribute> nastavena na `false`.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Je bezpečné potlačit upozornění tohoto pravidla, pokud je určitá klienty modulu COM jazyka Visual Basic 6 nebude mít přístup k typu.

## <a name="example"></a>Příklad
 Následující příklad ukazuje typ, který porušuje pravidla.

 [!code-csharp[FxCop.Interoperability.LongArgument#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Interoperability.LongArgument/cs/FxCop.Interoperability.LongArgument.cs#1)]
 [!code-vb[FxCop.Interoperability.LongArgument#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Interoperability.LongArgument/vb/FxCop.Interoperability.LongArgument.vb#1)]

## <a name="related-rules"></a>Související pravidla
 [CA1413: Vyhněte se neveřejným polím v hodnotách viditelných modulem COM](../code-quality/ca1413-avoid-non-public-fields-in-com-visible-value-types.md)

 [CA1407: Vyhněte se statickým členům ve viditelných typech modelu COM](../code-quality/ca1407-avoid-static-members-in-com-visible-types.md)

 [CA1017: Označte sestavení pomocí atributu ComVisibleAttribute](../code-quality/ca1017-mark-assemblies-with-comvisibleattribute.md)

## <a name="see-also"></a>Viz také
 [Spolupráce pomocí nespravovaného kódu](http://msdn.microsoft.com/library/ccb68ce7-b0e9-4ffb-839d-03b1cd2c1258) [Long – datový typ](http://msdn.microsoft.com/library/b4770c34-1804-4f8c-b512-c10b0893e516)



