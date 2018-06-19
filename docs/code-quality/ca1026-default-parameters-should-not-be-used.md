---
title: 'CA1026: Neměly by být použity výchozí parametry'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1026
- DefaultParametersShouldNotBeUsed
helpviewer_keywords:
- CA1026
- DefaultParametersShouldNotBeUsed
ms.assetid: 09643415-36ef-4d0f-9411-5721e14e2512
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7bf28c16bc5457309c2de42d79574dbb64739d9e
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31901644"
---
# <a name="ca1026-default-parameters-should-not-be-used"></a>CA1026: Neměly by být použity výchozí parametry
|||
|-|-|
|TypeName|DefaultParametersShouldNotBeUsed|
|CheckId|CA1026|
|Kategorie|Microsoft.Design|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Typ externě viditelné obsahuje metodu externě viditelné, která používá výchozí parametr.

## <a name="rule-description"></a>Popis pravidla
 Metody, které používají výchozí parametry jsou povoleny v části specifikace CLS (Common Language); specifikace CLS však umožňuje kompilátory Ignorovat hodnoty, které jsou přiřazeny k tyto parametry. Kód, který je napsán pro kompilátory, které ignorovat výchozí hodnoty parametrů nutné explicitně zadat argumenty pro každou výchozí parametr. Pokud chcete zachovat chování, které chcete napříč programovacích jazyků, měl by být nahrazen metody, které používají výchozí parametry přetížení metody, které poskytují výchozí parametry.

 Kompilátor ignoruje hodnoty parametrů výchozí spravovaných rozšíření pro C++ při přístupu ke spravovaného kódu. Visual Basic – kompilátor podporuje metody, které mají výchozí parametry, které používají [volitelné](/dotnet/visual-basic/language-reference/modifiers/optional) – klíčové slovo.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li porušení toto pravidlo, nahraďte metodu, která používá výchozí parametry s přetížení metody, které poskytují výchozí parametry.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo.

## <a name="example"></a>Příklad
 Následující příklad ukazuje metodu, která používá výchozí hodnoty parametrů a přetížené metody, které poskytují ekvivalentní funkce.

 [!code-vb[FxCop.Design.DefaultParameters#1](../code-quality/codesnippet/VisualBasic/ca1026-default-parameters-should-not-be-used_1.vb)]

## <a name="related-rules"></a>Související pravidla
 [CA1025: Nahraďte opakované argumenty polem parametrů](../code-quality/ca1025-replace-repetitive-arguments-with-params-array.md)

## <a name="see-also"></a>Viz také
 [Jazyková nezávislost a jazykově nezávislé komponenty](/dotnet/standard/language-independence-and-language-independent-components)