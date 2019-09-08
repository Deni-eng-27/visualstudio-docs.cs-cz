---
title: 'CA1821: Odeberte prázdné finalizační metody'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- RemoveEmptyFinalizers
- CA1821
helpviewer_keywords:
- CA1821
ms.assetid: 3f4855a0-e4a0-46e6-923c-4c3b7074048d
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f616547738c7c58d61289b2be71c8e56a1a427c8
ms.sourcegitcommit: 0f44ec8ba0263056ad04d2d0dc904ad4206ce8fc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/06/2019
ms.locfileid: "70766078"
---
# <a name="ca1821-remove-empty-finalizers"></a>CA1821: Odeberte prázdné finalizační metody

|||
|-|-|
|TypeName|RemoveEmptyFinalizers|
|CheckId|CA1821|
|Kategorie|Microsoft. Performance|
|Narušující změna|Nenarušující|

## <a name="cause"></a>příčina

Typ implementuje finalizační metodu, která je prázdná, volá pouze finalizační metodu základního typu nebo volá pouze podmíněně emitované metody.

## <a name="rule-description"></a>Popis pravidla

Kdykoli je to možné, vyhněte se finalizační metody z důvodu dalších režijních výkonů, které jsou součástí sledování životního cyklu objektu. Systém uvolňování paměti spustí finalizační metodu před tím, než objekt shromáždí. To znamená, že pro shromáždění objektu jsou vyžadovány alespoň dvě kolekce. Prázdná finalizační metoda má tuto přidanou režii bez jakýchkoli výhod.

## <a name="how-to-fix-violations"></a>Jak opravit porušení

Odeberte prázdný finalizační metodu. Pokud je pro ladění vyžadován finalizační metoda, vložte celý finalizační metodu do `#if DEBUG / #endif` direktiv.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Potlačit zprávu od tohoto pravidla.

## <a name="example"></a>Příklad

Následující příklad ukazuje prázdný finalizační metodu, která by měla být odebrána, finalizační metoda, která by měla být uzavřena `#if DEBUG / #endif` do direktiv a finalizační metoda, která `#if DEBUG / #endif` používá direktivy správně.

[!code-csharp[FxCop.Performance.RemoveEmptyFinalizers#1](../code-quality/codesnippet/CSharp/ca1821-remove-empty-finalizers_1.cs)]
