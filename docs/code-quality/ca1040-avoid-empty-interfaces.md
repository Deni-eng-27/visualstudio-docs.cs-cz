---
title: 'CA1040: Vyhněte se prázdným rozhraním'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- CA1040
- AvoidEmptyInterfaces
helpviewer_keywords:
- AvoidEmptyInterfaces
- CA1040
ms.assetid: 120a741b-5fd1-4836-8453-7857e0cd0380
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: ffdea7cadbf7bfc2803573a78fdd9bbc74b1d287
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54936863"
---
# <a name="ca1040-avoid-empty-interfaces"></a>CA1040: Vyhněte se prázdným rozhraním

|||
|-|-|
|TypeName|AvoidEmptyInterfaces|
|CheckId|CA1040|
|Kategorie|Microsoft.Design|
|Narušující změna|Narušující|

## <a name="cause"></a>Příčina
 Rozhraní není deklarovat všechny členy nebo implementovat dvě nebo více rozhraní.

## <a name="rule-description"></a>Popis pravidla
 Rozhraní definují členy ujednávající jejich chování nebo užití. Funkčnost popsaná rozhraním může být osvojena libovolným typem bez ohledu na to, kde se typ vyskytuje v hierarchii dědičnosti. Typ implementuje rozhraní tím, že poskytuje implementace jeho členů. Prázdné rozhraní nedefinuje žádné členy. Nedefinuje proto kontrakt, který je možné implementovat.

 Pokud váš návrh obsahuje prázdný implementovat rozhraní, které typy se očekává, pravděpodobně používáte rozhraní jako značku nebo způsob, jak identifikovat skupinu typů. Pokud tato identifikace dojde za běhu, je správný způsob, jak toho dosáhnout pomocí vlastního atributu. Přítomnost nebo absence atributu nebo vlastnosti atributu, použijte k identifikaci cílové typy. Je-li označením se musí vyskytovat v době kompilace, je nepřijatelné využívat prázdné rozhraní.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Odebrat rozhraní nebo přidat členy do něj. Pokud prázdné rozhraní používá k označení sadu typů, nahraďte rozhraní vlastního atributu.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Je bezpečné potlačit upozornění tohoto pravidla, pokud rozhraní se používá k identifikaci sadu typů v době kompilace.

## <a name="example"></a>Příklad
 Následující příklad ukazuje prázdné rozhraní.

 [!code-csharp[FxCop.Design.InterfacesNotEmpty#1](../code-quality/codesnippet/CSharp/ca1040-avoid-empty-interfaces_1.cs)]
 [!code-cpp[FxCop.Design.InterfacesNotEmpty#1](../code-quality/codesnippet/CPP/ca1040-avoid-empty-interfaces_1.cpp)]
 [!code-vb[FxCop.Design.InterfacesNotEmpty#1](../code-quality/codesnippet/VisualBasic/ca1040-avoid-empty-interfaces_1.vb)]