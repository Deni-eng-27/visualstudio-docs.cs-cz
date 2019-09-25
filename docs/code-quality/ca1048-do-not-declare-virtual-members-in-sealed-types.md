---
title: 'CA1048: Nedeklarujte virtuální členy v zapečetěných typech'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- DoNotDeclareVirtualMembersInSealedTypes
- CA1048
helpviewer_keywords:
- DoNotDeclareVirtualMembersInSealedTypes
- CA1048
ms.assetid: 5dcf4a30-6f98-48a8-b8cc-7b89ea757262
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: be0e1b4865b19930f8ddf7163a36b71123bb3a55
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/24/2019
ms.locfileid: "71235718"
---
# <a name="ca1048-do-not-declare-virtual-members-in-sealed-types"></a>CA1048: Nedeklarujte virtuální členy v zapečetěných typech

|||
|-|-|
|TypeName|DoNotDeclareVirtualMembersInSealedTypes|
|CheckId|CA1048|
|Kategorie|Microsoft.Design|
|Zásadní změna|Narušující|

## <a name="cause"></a>příčina
Veřejný typ je zapečetěn a deklaruje metodu, která je současně `virtual` (`Overridable` v Visual Basic), a není finální. Toto pravidlo neoznamuje porušení pro typy delegátů, které musí následovat po tomto vzoru.

## <a name="rule-description"></a>Popis pravidla
Typy deklarují metody jako virtuální, aby odvozující typy mohly přepsat implementaci virtuální metody. Podle definice nemůžete dědit z zapečetěného typu a vytvoření virtuální metody u zapečetěného typu bez významů.

Visual Basic a C# kompilátory neumožňují typům porušovat toto pravidlo.

## <a name="how-to-fix-violations"></a>Jak opravit porušení
Chcete-li opravit porušení tohoto pravidla, nastavte metodu jako nevirtuální, nebo zajistěte, aby byl typ dědičný.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
Nepotlačujte upozornění na toto pravidlo. Ponechání typu v aktuálním stavu může způsobit problémy s údržbou a neposkytuje žádné výhody.

## <a name="example"></a>Příklad
Následující příklad ukazuje typ, který je v rozporu s tímto pravidlem.

[!code-cpp[FxCop.Design.SealedVirtual#1](../code-quality/codesnippet/CPP/ca1048-do-not-declare-virtual-members-in-sealed-types_1.cpp)]