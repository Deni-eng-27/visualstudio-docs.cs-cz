---
title: 'CA1058: Typy by neměly rozšířit určité základní typy | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- TypesShouldNotExtendCertainBaseTypes
- CA1058
helpviewer_keywords:
- CA1058
- TypesShouldNotExtendCertainBaseTypes
ms.assetid: 8446ee40-beb1-49fa-8733-4d8e813471c0
caps.latest.revision: 26
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 1ce67a70b6cbe955ef13bf6475a672bcbb687d95
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68200453"
---
# <a name="ca1058-types-should-not-extend-certain-base-types"></a>CA1058: Typy by neměly rozšiřovat určité základní typy
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|TypesShouldNotExtendCertainBaseTypes|
|CheckId|CA1058|
|Kategorie|Microsoft.Design|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Externě viditelný typ rozšiřuje určité základní typy. Toto pravidlo v současné době sestavy typy, které jsou odvozeny z následujících typů:

- <xref:System.ApplicationException?displayProperty=fullName>

- <xref:System.Xml.XmlDocument?displayProperty=fullName>

- <xref:System.Collections.CollectionBase?displayProperty=fullName>

- <xref:System.Collections.DictionaryBase?displayProperty=fullName>

- <xref:System.Collections.Queue?displayProperty=fullName>

- <xref:System.Collections.ReadOnlyCollectionBase?displayProperty=fullName>

- <xref:System.Collections.SortedList?displayProperty=fullName>

- <xref:System.Collections.Stack?displayProperty=fullName>

## <a name="rule-description"></a>Popis pravidla
 Pro [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] verze 1 se doporučuje k odvození nové výjimky z <xref:System.ApplicationException>. Došlo ke změně doporučení a nové výjimky musí být odvozený z: <xref:System.Exception?displayProperty=fullName> nebo jeden z jejích podtříd v <xref:System> oboru názvů.

 Nelze vytvořit podtřídu <xref:System.Xml.XmlDocument> Pokud budete chtít vytvořit zobrazení základní objekt model nebo zdroj dat XML.

### <a name="non-generic-collections"></a>Obecné kolekce
 Použít a/nebo rozšířit obecných kolekcí, kdykoli je to možné. Pokud dříve dodán se netýkají obecné kolekce ve vašem kódu.

 **Příklady nesprávné použití**

```csharp
public class MyCollection : CollectionBase
{
}

public class MyReadOnlyCollection : ReadOnlyCollectionBase
{
}
```

 **Příklady správné použití**

```csharp
public class MyCollection : Collection<T>
{
}

public class MyReadOnlyCollection : ReadOnlyCollection<T>
{
}
```

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, odvodit typ z různých základního typu nebo obecné kolekce.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění tohoto pravidla pro porušení o <xref:System.ApplicationException>. Je bezpečné potlačit upozornění tohoto pravidla pro porušení o <xref:System.Xml.XmlDocument>. Je bezpečné pro potlačení varování týkající se obecné kolekce, pokud kód byla vydána dříve.
