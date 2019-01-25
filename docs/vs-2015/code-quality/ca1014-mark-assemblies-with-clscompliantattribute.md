---
title: 'CA1014: Označte sestavení pomocí atributu CLSCompliantAttribute | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1014
- MarkAssembliesWithClsCompliant
helpviewer_keywords:
- CA1014
- MarkAssembliesWithClsCompliant
ms.assetid: 4fe57449-cf45-4745-bcd2-6345f1ed266d
caps.latest.revision: 20
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 617f409eef099b78debacfe09c68a7f516cf7050
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54762951"
---
# <a name="ca1014-mark-assemblies-with-clscompliantattribute"></a>CA1014: Označte sestavení pomocí CLSCompliantAttribute
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|MarkAssembliesWithClsCompliant|
|CheckId|CA1014|
|Kategorie|Microsoft.Design|
|Narušující změna|Nenarušující|

## <a name="cause"></a>Příčina
 Sestavení nemá <xref:System.CLSCompliantAttribute?displayProperty=fullName> byt aplikovaný atribut.

## <a name="rule-description"></a>Popis pravidla
 Specifikace Common Language Specification (CLS) definuje omezení názvů, datové typy a pravidla, která musí sestavení dodržovat, pokud budou použita napříč programovacími jazyky. Dobrý návrh přikazuje, aby všechna sestavení explicitně uvedla dodržování specifikace CLS <xref:System.CLSCompliantAttribute>. Pokud atribut není v sestavení přítomen, nedodržuje sestavení předpisy.

 Je možné, kompatibilní se Specifikací CLS sestavení obsahují typy nebo členy, které nejsou kompatibilní s typu.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, přidejte atribut do sestavení. Namísto označení celé sestavení jako nesplňující požadavky, měli byste určit, které typ nebo členy typu jsou nekompatibilní a označte tyto prvky jako takové. Pokud je to možné by měl poskytovat alternativy CLS pro členy nesplňující požadavky, aby na nejširší možné cílovou skupinu dostanete všechny funkce, které jsou součástí vašeho sestavení.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo. Pokud nechcete, aby sestavení, aby vyhovoval předpisům, použijte atribut a nastavte jej na hodnotu `false`.

## <a name="example"></a>Příklad
 Následující příklad ukazuje sestavení, který má <xref:System.CLSCompliantAttribute?displayProperty=fullName> atribut, který deklaruje kompatibilní se Specifikací CLS.

 [!code-cpp[FxCop.Design.AssembliesCls#1](../snippets/cpp/VS_Snippets_CodeAnalysis/FxCop.Design.AssembliesCls/cpp/FxCop.Design.AssembliesCls.cpp#1)]
 [!code-csharp[FxCop.Design.AssembliesCls#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.AssembliesCls/cs/FxCop.Design.AssembliesCls.cs#1)]
 [!code-vb[FxCop.Design.AssembliesCls#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.AssembliesCls/vb/FxCop.Design.AssembliesCls.vb#1)]

## <a name="see-also"></a>Viz také
 <xref:System.CLSCompliantAttribute?displayProperty=fullName> [Jazyková nezávislost a jazykově nezávislé komponenty](http://msdn.microsoft.com/library/4f0b77d0-4844-464f-af73-6e06bedeafc6)
