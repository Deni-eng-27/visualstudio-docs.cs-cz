---
title: 'CA2227: Vlastnosti kolekce by měly být jen pro čtení | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology: vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- CA2227
- CollectionPropertiesShouldBeReadOnly
helpviewer_keywords:
- CA2227
- CollectionPropertiesShouldBeReadOnly
ms.assetid: 26967aaf-6fbe-438a-b4d3-ac579b5dc0f9
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: d55dd65fe7696fe7d9d6d453043314f64d951ebb
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53820511"
---
# <a name="ca2227-collection-properties-should-be-read-only"></a>CA2227: Vlastnosti kolekce by měly být jen pro čtení
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|CollectionPropertiesShouldBeReadOnly|
|CheckId|CA2227|
|Kategorie|Microsoft.Usage|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Externě viditelný zapisovatelnou vlastnost je typ, který implementuje <xref:System.Collections.ICollection?displayProperty=fullName>. Pole, indexery (vlastnosti s názvem "Položka") a sady oprávnění se ignorují pravidlem.

## <a name="rule-description"></a>Popis pravidla
 Zapisovatelná vlastnost kolekce umožňuje uživateli nahradit kolekci zcela jinou kolekci. Vlastnost jen pro čtení neumožňuje kolekci nahradit, ale stále umožňuje nastavit jednotlivé členy. Pokud nahrazující kolekce je cíl, vzor upřednostňovaný návrh je metoda odebrání všechny elementy z kolekce a způsob, jak znovu naplňte kolekce. Najdete v článku <xref:System.Collections.ArrayList.Clear%2A> a <xref:System.Collections.ArrayList.AddRange%2A> metody <xref:System.Collections.ArrayList?displayProperty=fullName> třídy příklad tohoto modelu.

 Binární soubor a serializace XML podporují jen pro čtení vlastnosti, které jsou kolekce. <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> Třída má specifické požadavky na typy, které implementují <xref:System.Collections.ICollection> a <xref:System.Collections.IEnumerable?displayProperty=fullName> -li být serializovatelný.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, nastavte vlastnost jen pro čtení a pokud to vyžaduje návrh, přidejte metody, zrušte a znovu naplňte kolekce.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo.

## <a name="example"></a>Příklad
 Následující příklad ukazuje typ s zapisovatelná vlastnost kolekce a jak kolekce se dá nahradit přímo. Kromě toho upřednostňovaný způsob nahrazení vlastnost kolekce jenom pro čtení pomocí `Clear` a `AddRange` metody se zobrazí.

 [!code-cpp[FxCop.Usage.PropertiesReturningCollections#1](../snippets/cpp/VS_Snippets_CodeAnalysis/FxCop.Usage.PropertiesReturningCollections/cpp/FxCop.Usage.PropertiesReturningCollections.cpp#1)]
 [!code-csharp[FxCop.Usage.PropertiesReturningCollections#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.PropertiesReturningCollections/cs/FxCop.Usage.PropertiesReturningCollections.cs#1)]
 [!code-vb[FxCop.Usage.PropertiesReturningCollections#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Usage.PropertiesReturningCollections/vb/FxCop.Usage.PropertiesReturningCollections.vb#1)]

## <a name="related-rules"></a>Související pravidla
 [CA1819: Vlastnosti by neměly vracet pole](../code-quality/ca1819-properties-should-not-return-arrays.md)
