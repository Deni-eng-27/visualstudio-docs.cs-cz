---
title: 'CA1708: Identifikátory by se měly lišit více než použitím malých a velkých písmen'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- IdentifiersShouldDifferByMoreThanCase
- CA1708
helpviewer_keywords:
- CA1708
- IdentifiersShouldDifferByMoreThanCase
ms.assetid: dac0f01d-dd21-484d-add1-c8cd2bf6969f
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 092b5f7db63ef83fb4d3bfb8507fdf7e0d5a6c86
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55040499"
---
# <a name="ca1708-identifiers-should-differ-by-more-than-case"></a>CA1708: Identifikátory by se měly lišit více než použitím malých a velkých písmen

|||
|-|-|
|TypeName|IdentifiersShouldDifferByMoreThanCase|
|CheckId|CA1708|
|Kategorie|Microsoft.Naming|
|Narušující změna|Narušující|

## <a name="cause"></a>Příčina
 Názvy dva typy, členy, parametry nebo plně kvalifikovaný obory názvů jsou identické, když jsou převedeny na malá písmena.

## <a name="rule-description"></a>Popis pravidla
 Identifikátory pro obory názvů, typy, členy a parametry nelze odlišit pouze ve velikosti písmen, protože jazyky cílené na modul CLR (Common Language Runtime) nemusí rozlišovat malá a velká písmena. Například [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] je často používaný jazyk velká a malá písmena.

 Toto pravidlo je vyvoláno na veřejně viditelné pouze členy.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Vyberte název, který je jedinečný, je porovnání pro jiné identifikátory písmen.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo. Knihovny nemusí být použitelná ve všech jazycích k dispozici v rozhraní .NET Framework.

## <a name="example-of-a-violation"></a>Příkladem porušení
 Následující příklad ukazuje porušení tohoto pravidla.

 [!code-csharp[FxCop.Naming.IdentifiersShouldDifferByMoreThanCase#1](../code-quality/codesnippet/CSharp/ca1708-identifiers-should-differ-by-more-than-case_1.cs)]

## <a name="related-rules"></a>Související pravidla
 [CA1709: Identifikátory by měly správně formátováno.](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)