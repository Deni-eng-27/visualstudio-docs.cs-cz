---
title: 'CA1401: Volání nespravovaných kódů by neměla být viditelná'
ms.date: 11/04/2016
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
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: b06aa26b046743b06f8fdd274da7a804a5ec06f6
ms.sourcegitcommit: 485ffaedb1ade71490f11cf05962add1718945cc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/16/2019
ms.locfileid: "72440719"
---
# <a name="ca1401-pinvokes-should-not-be-visible"></a>CA1401: Volání nespravovaných kódů by neměla být viditelná

|||
|-|-|
|TypeName|PInvokesShouldNotBeVisible|
|CheckId|CA1401|
|Kategorie|Microsoft. interoperabilita|
|Zásadní změna|Narušující|

## <a name="cause"></a>příčina
Veřejná nebo chráněná metoda ve veřejném typu má atribut <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName> (je implementován také klíčovým slovem `Declare` v [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]).

## <a name="rule-description"></a>Popis pravidla
Metody označené atributem <xref:System.Runtime.InteropServices.DllImportAttribute> (nebo metody, které jsou definovány pomocí klíčového slova `Declare` v [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]) používají pro přístup k nespravovanému kódu služby volání platformy. Tyto metody by neměly být vystaveny. Udržováním těchto metod jako soukromých nebo interních se ujistěte, že vaše knihovna nemůže být použita k porušení zabezpečení tím, že umožňuje volajícím přístup k nespravovaným rozhraním API, která by nemohly volat jinak.

## <a name="how-to-fix-violations"></a>Jak opravit porušení
Chcete-li opravit porušení tohoto pravidla, změňte úroveň přístupu metody.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
Nepotlačujte upozornění na toto pravidlo.

## <a name="example"></a>Příklad
Následující příklad deklaruje metodu, která porušuje toto pravidlo.

[!code-vb[FxCop.Interoperability.DllImports#1](../code-quality/codesnippet/VisualBasic/ca1401-p-invokes-should-not-be-visible_1.vb)]
[!code-csharp[FxCop.Interoperability.DllImports#1](../code-quality/codesnippet/CSharp/ca1401-p-invokes-should-not-be-visible_1.cs)]
