---
title: 'CA1058: Typy by neměly rozšiřovat určité základní typy'
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- TypesShouldNotExtendCertainBaseTypes
- CA1058
helpviewer_keywords:
- CA1058
- TypesShouldNotExtendCertainBaseTypes
ms.assetid: 8446ee40-beb1-49fa-8733-4d8e813471c0
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: fa1ffbb393700647f12c455c8d1307a77548f2d1
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/24/2019
ms.locfileid: "71235498"
---
# <a name="ca1058-types-should-not-extend-certain-base-types"></a>CA1058: Typy by neměly rozšiřovat určité základní typy

|||
|-|-|
|TypeName|TypesShouldNotExtendCertainBaseTypes|
|CheckId|CA1058|
|Kategorie|Microsoft.Design|
|Zásadní změna|Narušující|

## <a name="cause"></a>příčina

Typ rozšiřuje jeden z následujících základních typů:

- <xref:System.ApplicationException?displayProperty=fullName>
- <xref:System.Xml.XmlDocument?displayProperty=fullName>
- <xref:System.Collections.CollectionBase?displayProperty=fullName>
- <xref:System.Collections.DictionaryBase?displayProperty=fullName>
- <xref:System.Collections.Queue?displayProperty=fullName>
- <xref:System.Collections.ReadOnlyCollectionBase?displayProperty=fullName>
- <xref:System.Collections.SortedList?displayProperty=fullName>
- <xref:System.Collections.Stack?displayProperty=fullName>

Ve výchozím nastavení toto pravidlo vyhledává pouze externě viditelné typy, ale je možné jej [nakonfigurovat](#configurability).

## <a name="rule-description"></a>Popis pravidla

Výjimky by měly odvozovat z <xref:System.Exception?displayProperty=fullName> nebo jedné z jejích podtříd <xref:System> v oboru názvů.

Nevytvářejte podtřídu, <xref:System.Xml.XmlDocument> Pokud chcete vytvořit zobrazení XML základního objektového modelu nebo zdroje dat.

### <a name="non-generic-collections"></a>Neobecné kolekce

Pokud je to možné, používejte a rozšíříte obecné kolekce. Nezvětšujte neobecné kolekce v kódu, pokud jste ho předtím dodali.

**Příklady nesprávného použití**

```csharp
public class MyCollection : CollectionBase
{
}

public class MyReadOnlyCollection : ReadOnlyCollectionBase
{
}
```

**Příklady správného použití**

```csharp
public class MyCollection : Collection<T>
{
}

public class MyReadOnlyCollection : ReadOnlyCollection<T>
{
}
```

## <a name="how-to-fix-violations"></a>Jak opravit porušení

Chcete-li opravit porušení tohoto pravidla, odvodit typ z jiného základního typu nebo z obecné kolekce.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Potlačit upozornění z tohoto pravidla pro porušení <xref:System.ApplicationException>. Z tohoto pravidla je bezpečné potlačit upozornění, které se týká <xref:System.Xml.XmlDocument>porušení. Je bezpečné potlačit upozornění na neobecnou kolekci, pokud byl kód vydaný dříve.

## <a name="configurability"></a>Konfigurovatelnost

Pokud toto pravidlo spouštíte z [analyzátorů FxCop](install-fxcop-analyzers.md) (a ne pomocí starší verze analýzy), můžete nakonfigurovat, které části základu kódu mají spustit toto pravidlo, na základě jejich přístupnosti. Například chcete-li určit, že pravidlo by mělo běžet pouze proti neveřejnému povrchu rozhraní API, přidejte do souboru. editorconfig v projektu následující dvojici klíč-hodnota:

```ini
dotnet_code_quality.ca1058.api_surface = private, internal
```

Tuto možnost můžete nakonfigurovat jenom pro toto pravidlo, pro všechna pravidla nebo pro všechna pravidla v této kategorii (návrh). Další informace najdete v tématu [Konfigurace analyzátorů FxCop](configure-fxcop-analyzers.md).