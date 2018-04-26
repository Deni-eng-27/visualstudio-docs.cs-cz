---
title: 'CA1401: P vyvolá by neměly být viditelné'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- PInvokesShouldNotBeVisible
- CA1401
helpviewer_keywords:
- CA1401
- PInvokesShouldNotBeVisible
ms.assetid: 0f4d96c1-f9de-414e-b223-4dc7f691bee3
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c2aaadb0570e47e5ef41614925c20f8dc30f1620
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="ca1401-pinvokes-should-not-be-visible"></a>CA1401: Volání nespravovaných kódů by neměla být viditelná
|||
|-|-|
|TypeName|PInvokesShouldNotBeVisible|
|CheckId|CA1401|
|Kategorie|Microsoft.Interoperability|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Metoda veřejných nebo chráněné v veřejného typu má <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName> atribut (také implementované `Declare` – klíčové slovo v [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]).

## <a name="rule-description"></a>Popis pravidla
 Metody, které jsou označené <xref:System.Runtime.InteropServices.DllImportAttribute> atribut (nebo metody, které jsou definované pomocí `Declare` – klíčové slovo v [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]) používat služby vyvolání platformy pro přístup k nespravovaného kódu. Tyto metody by neměly být vystaveny. Udržováním tyto metody soukromý nebo interní, zajistíte, že porušení zabezpečení tím, že volající přístup k nespravovaného rozhraní API, které nelze volat v opačném případě nelze použít knihovnu.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Opravit porušení toto pravidlo, změňte úroveň přístupu metody.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo.

## <a name="example"></a>Příklad
 Následující příklad deklaruje metodu, která porušuje toto pravidlo.

 [!code-vb[FxCop.Interoperability.DllImports#1](../code-quality/codesnippet/VisualBasic/ca1401-p-invokes-should-not-be-visible_1.vb)]
 [!code-csharp[FxCop.Interoperability.DllImports#1](../code-quality/codesnippet/CSharp/ca1401-p-invokes-should-not-be-visible_1.cs)]