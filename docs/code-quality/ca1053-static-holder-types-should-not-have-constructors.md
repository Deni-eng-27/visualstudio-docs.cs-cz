---
title: 'CA1053: Statický vlastník typů by neměl mít konstruktory'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- StaticHolderTypesShouldNotHaveConstructors
- CA1053
helpviewer_keywords:
- CA1053
- StaticHolderTypesShouldNotHaveConstructors
ms.assetid: 10302b9a-fa5e-4935-a06a-513d9600f613
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f63a5017b5bd3b552882a11d9796af2530dd5634
ms.sourcegitcommit: 485ffaedb1ade71490f11cf05962add1718945cc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/16/2019
ms.locfileid: "72449113"
---
# <a name="ca1053-static-holder-types-should-not-have-default-constructors"></a>CA1053: statické typy držitelů by neměly mít výchozí konstruktory

|||
|-|-|
|TypeName|StaticHolderTypesShouldNotHaveConstructors|
|CheckId|CA1053|
|Kategorie|Microsoft. Design|
|Zásadní změna|Narušující|

> [!NOTE]
> Pravidlo CA1053 je kombinované do [CA1052: statické typy držitelů by měly být zapečetěné](ca1052-static-holder-types-should-be-sealed.md) v [analyzátorech FxCop](fxcop-analyzers.yml).

## <a name="cause"></a>příčina

Veřejný nebo vnořený veřejný typ deklaruje pouze statické členy a má výchozí konstruktor.

## <a name="rule-description"></a>Popis pravidla

Výchozí konstruktor není potřebný, protože volání statických členů nevyžaduje instanci typu. Vzhledem k tomu, že typ nemá nestatické členy, vytvoření instance neposkytuje přístup k žádnému z členů typu.

## <a name="how-to-fix-violations"></a>Jak opravit porušení

Chcete-li opravit porušení tohoto pravidla, odeberte výchozí konstruktor.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Nepotlačujte upozornění na toto pravidlo. Přítomnost výchozího konstruktoru naznačuje, že typ není statický typ.
