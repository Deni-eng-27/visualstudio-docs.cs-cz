---
title: 'CA2227: Vlastnosti kolekce by měly být pouze pro čtení'
ms.date: 09/28/2018
ms.topic: reference
f1_keywords:
- CA2227
- CollectionPropertiesShouldBeReadOnly
helpviewer_keywords:
- CA2227
- CollectionPropertiesShouldBeReadOnly
ms.assetid: 26967aaf-6fbe-438a-b4d3-ac579b5dc0f9
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
- CPP
ms.workload:
- multiple
ms.openlocfilehash: be864812cc7355f80700bd3e270178c9626d4180
ms.sourcegitcommit: 034c503ae04e22cf840ccb9770bffd012e40fb2d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/14/2019
ms.locfileid: "72305894"
---
# <a name="ca2227-collection-properties-should-be-read-only"></a>CA2227: Vlastnosti kolekce by měly být pouze pro čtení

|||
|-|-|
|TypeName|CollectionPropertiesShouldBeReadOnly|
|CheckId|CA2227|
|Category|Microsoft.Usage|
|Zásadní změna|Narušující|

## <a name="cause"></a>Příčina

Externě viditelná vlastnost s možností zápisu je typu, který implementuje <xref:System.Collections.ICollection?displayProperty=fullName>. Toto pravidlo ignoruje pole, indexery (vlastnosti s názvem Item) a sady oprávnění.

## <a name="rule-description"></a>Popis pravidla

Vlastnost zapisovatelné kolekce umožňuje uživateli nahradit kolekci zcela jinou kolekcí. Vlastnost jen pro čtení zastaví vyměnění kolekce, ale stále umožňuje nastavit jednotlivé členy. Pokud nahradíte kolekci cílem, preferovaný vzor návrhu je zahrnout metodu pro odebrání všech prvků z kolekce a metodu pro přeplnění kolekce. Příklad tohoto vzoru naleznete v tématu metody @no__t 0 a <xref:System.Collections.ArrayList.AddRange%2A> třídy <xref:System.Collections.ArrayList?displayProperty=fullName>.

Binární i XML serializace podporují vlastnosti jen pro čtení, které jsou kolekcemi. Třída <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> má specifické požadavky pro typy, které implementují <xref:System.Collections.ICollection> a <xref:System.Collections.IEnumerable?displayProperty=fullName>, aby bylo možné serializovat.

## <a name="how-to-fix-violations"></a>Jak opravit porušení

Chcete-li opravit porušení tohoto pravidla, nastavte vlastnost jen pro čtení. Pokud je návrh vyžaduje, přidejte metody, které vymaže a znovu naplní kolekci.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Můžete potlačit upozornění, pokud je vlastnost součástí třídy [přenos dat objektů (DTO)](/previous-versions/msp-n-p/ff649585(v=pandp.10)) .

V opačném případě potlačí upozornění z tohoto pravidla.

## <a name="example"></a>Příklad

Následující příklad ukazuje typ s zapisovatelnou vlastností Collection a ukazuje, jak lze kolekci nahradit přímo. Kromě toho zobrazuje preferovaný způsob nahrazení vlastnosti kolekce jen pro čtení pomocí metod `Clear` a `AddRange`.

[!code-csharp[FxCop.Usage.PropertiesReturningCollections#1](../code-quality/codesnippet/CSharp/ca2227-collection-properties-should-be-read-only_1.cs)]
[!code-vb[FxCop.Usage.PropertiesReturningCollections#1](../code-quality/codesnippet/VisualBasic/ca2227-collection-properties-should-be-read-only_1.vb)]
[!code-cpp[FxCop.Usage.PropertiesReturningCollections#1](../code-quality/codesnippet/CPP/ca2227-collection-properties-should-be-read-only_1.cpp)]

## <a name="related-rules"></a>Související pravidla

- [CA1819: Vlastnosti by neměly vracet pole @ no__t-0