---
title: 'CA1019: Definujte přístupové objekty pro argumenty atributů'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1019
- DefineAccessorsForAttributeArguments
helpviewer_keywords:
- CA1019
- DefineAccessorsForAttributeArguments
ms.assetid: 197f2378-3c43-427e-80de-9ec25006c05c
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: c53fe96163a3913c024eefeb5deb8a47df691e1f
ms.sourcegitcommit: 034c503ae04e22cf840ccb9770bffd012e40fb2d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/14/2019
ms.locfileid: "72306143"
---
# <a name="ca1019-define-accessors-for-attribute-arguments"></a>CA1019: Definujte přístupové objekty pro argumenty atributů

|||
|-|-|
|TypeName|DefineAccessorsForAttributeArguments|
|CheckId|CA1019|
|Category|Microsoft.Design|
|Zásadní změna|Nenarušující|

## <a name="cause"></a>Příčina
V konstruktoru definuje atribut argumenty, které nemají odpovídající vlastnosti.

## <a name="rule-description"></a>Popis pravidla
Atributy mohou definovat povinné argumenty, které musí být specifikovány při použití atributu na cíl. Říká se jim také poziční argumenty, jelikož jsou konstruktorům atributů předány jako poziční parametry. Pro každý povinný argument by měl atribut navíc poskytovat odpovídající vlastnost jen pro čtení, aby mohla být hodnota argumentu během spuštění získána. Toto pravidlo kontroluje, zda pro každý parametr konstruktoru jste definovali odpovídající vlastnost.

Atributy mohou také definovat volitelné argumenty, které jsou rovněž známy jako pojmenované argumenty. Tyto argumenty jsou podle názvu poskytovány konstruktorům atributů a měly by mít odpovídající vlastnost pro čtení i zápis.

U povinných a volitelných argumentů by odpovídající vlastnosti a parametry konstruktoru měly používat stejný název, ale různé velikosti písmen. Vlastnosti používají velká a malá písmena Pascal a parametry používají ve stylu CamelCase velká a malá písmena.

## <a name="how-to-fix-violations"></a>Jak opravit porušení
Chcete-li opravit porušení tohoto pravidla, přidejte vlastnost jen pro čtení pro každý parametr konstruktoru, který ho nemá.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
Pokud nechcete, aby se hodnota povinného argumentu dala získat, potlačíte upozornění od tohoto pravidla.

## <a name="custom-attributes-example"></a>Příklad vlastních atributů

Následující příklad ukazuje dva atributy, které definují povinný (poziční) parametr. První implementace atributu je nesprávně definovaná. Druhá implementace je správná.

[!code-csharp[FxCop.Design.AttributeAccessors#1](../code-quality/codesnippet/CSharp/ca1019-define-accessors-for-attribute-arguments_1.cs)]
[!code-vb[FxCop.Design.AttributeAccessors#1](../code-quality/codesnippet/VisualBasic/ca1019-define-accessors-for-attribute-arguments_1.vb)]

## <a name="positional-and-named-arguments"></a>Poziční a pojmenované argumenty

Poziční a pojmenované argumenty usnadňují uživatelům vaší knihovny, které argumenty jsou pro atribut povinné a které argumenty jsou nepovinné.

Následující příklad ukazuje implementaci atributu, který má oba poziční i pojmenované argumenty:

[!code-csharp[FxCop.Design.AttributeAccessorsNamed#1](../code-quality/codesnippet/CSharp/ca1019-define-accessors-for-attribute-arguments_2.cs)]

Následující příklad ukazuje, jak použít vlastní atribut na dvě vlastnosti:

[!code-csharp[FxCop.Design.AttributeAccessorsNamedApplied#1](../code-quality/codesnippet/CSharp/ca1019-define-accessors-for-attribute-arguments_3.cs)]

## <a name="related-rules"></a>Související pravidla
[CA1813: Vyhněte se nezapečetěným atributům @ no__t-0

## <a name="see-also"></a>Viz také:
[Atributy](/dotnet/standard/design-guidelines/attributes)