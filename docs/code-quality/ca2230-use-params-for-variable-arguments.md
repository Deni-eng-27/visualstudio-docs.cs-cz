---
title: 'CA2230: Použijte parametry pro proměnné argumenty'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- UseParamsForVariableArguments
- CA2230
helpviewer_keywords:
- CA2230
- UseParamsForVariableArguments
ms.assetid: bf98b733-4855-4110-9f16-eba5a9e79421
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b3318a9f5bd65c6b9514519936cc52e037e0c215
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62541780"
---
# <a name="ca2230-use-params-for-variable-arguments"></a>CA2230: Použijte parametry pro proměnné argumenty

|||
|-|-|
|TypeName|UseParamsForVariableArguments|
|CheckId|CA2230|
|Kategorie|Microsoft.Usage|
|Narušující změna|Narušující|

## <a name="cause"></a>Příčina
 Veřejný nebo chráněný typ obsahuje veřejná nebo chráněná metoda, která používá `VarArgs` konvence volání.

## <a name="rule-description"></a>Popis pravidla
 `VarArgs` Konvence volání se používá některé metody definicemi přijímajícími proměnný počet parametrů. Metoda použití `VarArgs` konvence volání není specifikace CLS (Common Language) předpisy a nemusí být přístupné napříč programovacími jazyky.

 V jazyce C# `VarArgs` konvence volání se používá při seznamu parametrů metod končí `__arglist` – klíčové slovo. Jazyk Visual Basic nepodporuje `VarArgs` volání konvence a Visual C++ umožňuje použití pouze v nespravovaném kódu, který používá tři tečky `...` zápis.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla v jazyce C#, použijte [params](/dotnet/csharp/language-reference/keywords/params) – klíčové slovo místo `__arglist`.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo.

## <a name="example"></a>Příklad
 Následující příklad ukazuje dva způsoby, ten, který porušuje pravidla a ten, který splňuje pravidlo.

 [!code-csharp[FxCop.Usage.UseParams#1](../code-quality/codesnippet/CSharp/ca2230-use-params-for-variable-arguments_1.cs)]

## <a name="see-also"></a>Viz také:

- <xref:System.Reflection.CallingConventions?displayProperty=fullName>
- [Jazyková nezávislost a jazykově nezávislé komponenty](/dotnet/standard/language-independence-and-language-independent-components)