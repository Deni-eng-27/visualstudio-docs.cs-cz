---
title: 'CA1047: Nedeklarujte chráněné členy v zapečetěných typech'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- DoNotDeclareProtectedMembersInSealedTypes
- CA1047
helpviewer_keywords:
- CA1047
- DoNotDeclareProtectedMembersInSealedTypes
ms.assetid: 829033b5-a9d8-4f26-a719-45494c9dd035
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 77277c093396ddbfdf458e93f468ad5ce5775bd2
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54928396"
---
# <a name="ca1047-do-not-declare-protected-members-in-sealed-types"></a>CA1047: Nedeklarujte chráněné členy v zapečetěných typech

|||
|-|-|
|TypeName|DoNotDeclareProtectedMembersInSealedTypes|
|CheckId|CA1047|
|Kategorie|Microsoft.Design|
|Narušující změna|Nenarušující|

## <a name="cause"></a>Příčina
 Je veřejný typ `sealed` (`NotInheritable` v jazyce Visual basic) a deklaruje chráněný člen nebo chráněné vnořeného typu. Toto pravidlo nevytváří sestavu porušení pro <xref:System.Object.Finalize%2A> metody, které musí postupovat podle tohoto vzoru.

## <a name="rule-description"></a>Popis pravidla
 Typy deklarují chráněné členy, aby k nim odvozené typy mohly přistupovat nebo je přepisovat. Podle definice nelze dědit ze zapečetěného typu, což znamená, že chráněné metody zapečetěných typů nelze volat.

 Kompilátor jazyka C# vyvolá upozornění pro tuto chybu.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, změnit úroveň přístupu členu na soukromý nebo učiňte typ odvoditelný.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo. Opuštění typu v jejím aktuálním stavu může způsobit problémy s údržbou a nepřináší žádné výhody.

## <a name="example"></a>Příklad
 Následující příklad ukazuje typ, který porušuje tato pravidla.

 [!code-vb[FxCop.Design.SealedNoProtected#1](../code-quality/codesnippet/VisualBasic/ca1047-do-not-declare-protected-members-in-sealed-types_1.vb)]
 [!code-csharp[FxCop.Design.SealedNoProtected#1](../code-quality/codesnippet/CSharp/ca1047-do-not-declare-protected-members-in-sealed-types_1.cs)]