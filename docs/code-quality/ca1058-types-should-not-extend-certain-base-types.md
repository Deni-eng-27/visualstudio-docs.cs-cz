---
title: "CA1058: Typy by neměly rozšířit určité základní typy | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- TypesShouldNotExtendCertainBaseTypes
- CA1058
helpviewer_keywords:
- CA1058
- TypesShouldNotExtendCertainBaseTypes
ms.assetid: 8446ee40-beb1-49fa-8733-4d8e813471c0
caps.latest.revision: "24"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 45cddd908c53d129a230b998c6dad03196a31c49
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="ca1058-types-should-not-extend-certain-base-types"></a>CA1058: Typy by neměly rozšířit určité základní typy
|||  
|-|-|  
|TypeName|TypesShouldNotExtendCertainBaseTypes|  
|CheckId|CA1058|  
|Kategorie|Microsoft.Design|  
|Narušující změna|Narušující|  
  
## <a name="cause"></a>příčina  
 Externě viditelný typ rozšiřuje určité základní typy. Toto pravidlo v současné době sestavy typy odvozené z následujících typů:  
  
-   <xref:System.ApplicationException?displayProperty=fullName>  
  
-   <xref:System.Xml.XmlDocument?displayProperty=fullName>  
  
-   <xref:System.Collections.CollectionBase?displayProperty=fullName>  
  
-   <xref:System.Collections.DictionaryBase?displayProperty=fullName>  
  
-   <xref:System.Collections.Queue?displayProperty=fullName>  
  
-   <xref:System.Collections.ReadOnlyCollectionBase?displayProperty=fullName>  
  
-   <xref:System.Collections.SortedList?displayProperty=fullName>  
  
-   <xref:System.Collections.Stack?displayProperty=fullName>  
  
## <a name="rule-description"></a>Popis pravidla  
 Pro [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] verze 1, se doporučuje odvodit nové výjimky z <xref:System.ApplicationException>. Doporučuje se změnila a nové výjimky by měl být odvozen z <xref:System.Exception?displayProperty=fullName> nebo jednoho z jeho podtřídy v <xref:System> oboru názvů.  
  
 Nevytvářejte podtřídou třídy <xref:System.Xml.XmlDocument> Pokud budete chtít vytvořit zobrazení základní objekt model nebo zdroj dat XML.  
  
### <a name="non-generic-collections"></a>Neobecné kolekce  
 Použít nebo rozšířit obecné kolekce, kdykoli je to možné. Pokud dříve dodávané se netýkají neobecnou kolekce ve vašem kódu.  
  
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
 Opravit porušení toto pravidlo, být typ odvozený od různých základní typ nebo obecnou kolekci.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Není potlačit upozornění od tohoto pravidla pro porušení o <xref:System.ApplicationException>. Je bezpečné upozornění od tohoto pravidla pro porušení potlačit o <xref:System.Xml.XmlDocument>. Je bezpečné pro potlačení upozornění týkající se negenerická kolekce, pokud byla dříve vydaná kód.