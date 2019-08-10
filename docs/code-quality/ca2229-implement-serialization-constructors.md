---
title: 'CA2229: Implementujte serializační konstruktory'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2229
- ImplementSerializationConstructors
helpviewer_keywords:
- CA2229
- ImplementSerializationConstructors
ms.assetid: 8e04d5fe-dfad-445a-972e-0648324fac45
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 11dfa98bb348f874a2774454cc465fb80cb71750
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68920168"
---
# <a name="ca2229-implement-serialization-constructors"></a>CA2229: Implementujte serializační konstruktory

|||
|-|-|
|TypeName|ImplementSerializationConstructors|
|CheckId|CA2229|
|Kategorie|Microsoft.Usage|
|Narušující změna|Bez přerušení|

## <a name="cause"></a>příčina
Typ implementuje <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName> rozhraní, není delegát nebo rozhraní a jedna z následujících podmínek je pravdivá:

- Typ nemá konstruktor, který přebírá <xref:System.Runtime.Serialization.SerializationInfo?displayProperty=fullName> objekt <xref:System.Runtime.Serialization.StreamingContext?displayProperty=fullName> a objekt (signatura konstruktoru serializace).

- Typ je nezapečetěný a modifikátor přístupu pro svůj Serializační konstruktor není chráněný (Family).

- Typ je zapečetěný a modifikátor přístupu pro svůj Serializační konstruktor není privátní.

## <a name="rule-description"></a>Popis pravidla
Toto pravidlo je relevantní pro typy, které podporují vlastní serializaci. Typ podporuje vlastní serializaci, pokud implementuje <xref:System.Runtime.Serialization.ISerializable> rozhraní. Konstruktor serializace je vyžadován k deserializaci nebo opětovnému vytvoření objektů, které byly serializovány pomocí <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A?displayProperty=fullName> metody.

## <a name="how-to-fix-violations"></a>Jak opravit porušení
Implementací konstruktoru serializace se vyřeší porušení tohoto pravidla. Pro zapečetěnou třídu musí být konstruktor soukromý. V ostatních případech musí být chráněný.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
Potlačit porušení pravidla Typ nebude deserializovatelný a nebude fungovat v mnoha scénářích.

## <a name="example"></a>Příklad
Následující příklad ukazuje typ, který splňuje pravidlo.

[!code-csharp[FxCop.Usage.ISerializableCtor#1](../code-quality/codesnippet/CSharp/ca2229-implement-serialization-constructors_1.cs)]

## <a name="related-rules"></a>Související pravidla
[CA2237: Označte typy ISerializable pomocí SerializableAttribute](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)

## <a name="see-also"></a>Viz také:

- <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName>
- <xref:System.Runtime.Serialization.SerializationInfo?displayProperty=fullName>
- <xref:System.Runtime.Serialization.StreamingContext?displayProperty=fullName>