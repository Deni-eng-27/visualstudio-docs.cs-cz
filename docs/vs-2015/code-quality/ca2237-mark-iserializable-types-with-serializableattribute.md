---
title: 'CA2237: Označte typy ISerializable pomocí SerializableAttribute | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2237
- MarkISerializableTypesWithSerializable
helpviewer_keywords:
- MarkISerializableTypesWithSerializable
- CA2237
ms.assetid: 9bd6bb24-a527-43dd-9952-043c0c694f46
caps.latest.revision: 15
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: d8778b0bfa035c782cf35d205fc59d463112196c
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "85545155"
---
# <a name="ca2237-mark-iserializable-types-with-serializableattribute"></a>CA2237: Označte typy ISerializable pomocí SerializableAttribute
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|Položka|Hodnota|
|-|-|
|TypeName|MarkISerializableTypesWithSerializable|
|CheckId|CA2237|
|Kategorie|Microsoft. Usage|
|Narušující změna|Bez přerušení|

## <a name="cause"></a>Příčina
 Externě viditelný typ implementuje <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName> rozhraní a typ není označen <xref:System.SerializableAttribute?displayProperty=fullName> atributem. Pravidlo ignoruje odvozené typy, jejichž základní typ není serializovatelný.

## <a name="rule-description"></a>Popis pravidla
 Aby je bylo možné rozpoznat modulem CLR (Common Language Runtime) jako serializovatelný, typy musí být označeny <xref:System.SerializableAttribute> atributem i v případě, že typ používá vlastní rutinu serializace prostřednictvím implementace <xref:System.Runtime.Serialization.ISerializable> rozhraní.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, použijte <xref:System.SerializableAttribute> atribut na typ.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Potlačit upozornění z tohoto pravidla pro třídy výjimek, protože musí být serializovatelný pro správné fungování napříč doménami aplikace.

## <a name="example"></a>Příklad
 Následující příklad ukazuje typ, který je v rozporu s pravidlem. Odkomentujte <xref:System.SerializableAttribute> řádek atributu pro splnění pravidla.

 [!code-csharp[FxCop.Usage.MarkSerializable#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.MarkSerializable/cs/FxCop.Usage.MarkSerializable.cs#1)]
 [!code-vb[FxCop.Usage.MarkSerializable#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Usage.MarkSerializable/vb/FxCop.Usage.MarkSerializable.vb#1)]

## <a name="related-rules"></a>Související pravidla
 [CA2236: Volejte metody základní třídy u typů ISerializable](../code-quality/ca2236-call-base-class-methods-on-iserializable-types.md)

 [CA2240: Implementujte správně ISerializable](../code-quality/ca2240-implement-iserializable-correctly.md)

 [CA2229: Implementujte serializační konstruktory](../code-quality/ca2229-implement-serialization-constructors.md)

 [CA2238: Implementujte správně metody serializace](../code-quality/ca2238-implement-serialization-methods-correctly.md)

 [CA2235: Označte všechna neserializovatelná pole](../code-quality/ca2235-mark-all-non-serializable-fields.md)

 [CA2239: Zadejte metody deserializace pro nepovinná pole](../code-quality/ca2239-provide-deserialization-methods-for-optional-fields.md)

 [CA2120: Zabezpečte serializační konstruktory](../code-quality/ca2120-secure-serialization-constructors.md)
