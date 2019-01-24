---
title: 'CA2235: Označte všechna neserializovatelná pole | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2235
- MarkAllNonSerializableFields
helpviewer_keywords:
- CA2235
- MarkAllNonSerializableFields
ms.assetid: 599ad877-3a15-426c-bf17-5de15427365f
caps.latest.revision: 15
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 542ace3c1e73454884fb341f5f9e38cf09d86396
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54773026"
---
# <a name="ca2235-mark-all-non-serializable-fields"></a>CA2235: Označte všechna neserializovatelná pole
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|MarkAllNonSerializableFields|
|CheckId|CA2235|
|Kategorie|Microsoft.Usage|
|Narušující změna|Pevné|

## <a name="cause"></a>Příčina
 Neserializovatelný typ pole instance je deklarován v serializovatelném typu.

## <a name="rule-description"></a>Popis pravidla
 Serializovatelný typ. je ten, který je označen <xref:System.SerializableAttribute?displayProperty=fullName> atribut. Když je typ serializován, <xref:System.Runtime.Serialization.SerializationException?displayProperty=fullName> je vyvolána výjimka, pokud typ obsahuje pole instance typu, který není serializovatelný.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, použijte <xref:System.NonSerializedAttribute?displayProperty=fullName> atributu na pole, který není serializovatelný.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Pouze v případě potlačit upozornění tohoto pravidla <xref:System.Runtime.Serialization.ISerializationSurrogate?displayProperty=fullName> typ je deklarován, která umožňuje instance pole, které chcete serializovat a deserializovat.

## <a name="example"></a>Příklad
 Následující příklad ukazuje typ, který porušuje pravidla a typ, který splňuje pravidlo.

 [!code-csharp[FxCop.Usage.MarkNonSerializable#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.MarkNonSerializable/cs/FxCop.Usage.MarkNonSerializable.cs#1)]
 [!code-vb[FxCop.Usage.MarkNonSerializable#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Usage.MarkNonSerializable/vb/FxCop.Usage.MarkNonSerializable.vb#1)]

## <a name="related-rules"></a>Související pravidla
 [CA2236: Volání metody třídy base na typech ISerializable](../code-quality/ca2236-call-base-class-methods-on-iserializable-types.md)

 [CA2240: Implementujte správně ISerializable](../code-quality/ca2240-implement-iserializable-correctly.md)

 [CA2229: Implementovat Serializační konstruktory](../code-quality/ca2229-implement-serialization-constructors.md)

 [CA2238: Implementujte správně metody serializace](../code-quality/ca2238-implement-serialization-methods-correctly.md)

 [CA2237: Označte typy ISerializable pomocí SerializableAttribute](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)

 [CA2239: Poskytujte metody deserializace pro nepovinné pole](../code-quality/ca2239-provide-deserialization-methods-for-optional-fields.md)

 [CA2120: Zabezpečte Serializační konstruktory](../code-quality/ca2120-secure-serialization-constructors.md)
