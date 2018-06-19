---
title: 'CA1000: Nedeklarujte statické členy v obecných typech'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1000
- DoNotDeclareStaticMembersOnGenericTypes
helpviewer_keywords:
- DoNotDeclareStaticMembersOnGenericTypes
- CA1000
ms.assetid: 5c0da594-f8d0-4f40-953d-56bf7fbd2087
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b491d49a6bd9a7ffc1164c6cfa45b5260b339192
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31899375"
---
# <a name="ca1000-do-not-declare-static-members-on-generic-types"></a>CA1000: Nedeklarujte statické členy v obecných typech
|||
|-|-|
|TypeName|DoNotDeclareStaticMembersOnGenericTypes|
|CheckId|CA1000|
|Kategorie|Microsoft.Design|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Obsahuje externě viditelné obecného typu `static` (`Shared` v jazyce Visual Basic) člena.

## <a name="rule-description"></a>Popis pravidla
 Když `static` obecný typ člena je volána, pro typ musí být zadána argumentem typu. Je-li zavolán obecný člen instance, který nepodporuje odvozování, musí být pro tento člen zadán argument typu. Syntaxe pro určení argument typu v obou případech je jiné a snadno zaměňovat, jak ukazují následující volání:

```vb
' Shared method in a generic type.
GenericType(Of Integer).SharedMethod()

' Generic instance method that does not support inference.
someObject.GenericMethod(Of Integer)()
```

```csharp
// Static method in a generic type.
GenericType<int>.StaticMethod();

// Generic instance method that does not support inference.
someObject.GenericMethod<int>();
```

 Obecně platí obě předchozí deklarace je nutno, aby argument typu není potřeba zadat, kdy se nazývá člen. Výsledkem syntaxi pro volání členy v obecných typech, které se neliší od syntaxe – obecné typy. Další informace najdete v tématu [CA1004: Obecné metody by měly poskytnout parametr typu](../code-quality/ca1004-generic-methods-should-provide-type-parameter.md).

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Opravit porušení toto pravidlo, odeberte statický člen, nebo ho změnit na instanci členu.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo. Poskytuje obecné typy v syntaxi, který se snadno pochopit a používat zkracuje čas, který je potřeba další a zvyšuje počet přijetí nové knihovny.

## <a name="related-rules"></a>Související pravidla
 [CA1005: Vyhněte se nadbytečným parametrům na obecných typech](../code-quality/ca1005-avoid-excessive-parameters-on-generic-types.md)

 [CA1010: Kolekce musí implementovat obecné rozhraní](../code-quality/ca1010-collections-should-implement-generic-interface.md)

 [CA1002: Nezveřejňujte obecné seznamy](../code-quality/ca1002-do-not-expose-generic-lists.md)

 [CA1006: Nevnořujte obecné typy v signaturách členu](../code-quality/ca1006-do-not-nest-generic-types-in-member-signatures.md)

 [CA1004: Obecné metody by měly poskytnout parametr typu](../code-quality/ca1004-generic-methods-should-provide-type-parameter.md)

 [CA1003: Použijte instance obecných obslužných rutin události](../code-quality/ca1003-use-generic-event-handler-instances.md)

 [CA1007: Použijte obecné typy, kde je to vhodné](../code-quality/ca1007-use-generics-where-appropriate.md)

## <a name="see-also"></a>Viz také
 [Obecné typy](/dotnet/csharp/programming-guide/generics/index)