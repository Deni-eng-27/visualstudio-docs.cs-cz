---
title: 'CA2137: Transparentní metody musí obsahovat pouze ověřitelné IL'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- CA2137
ms.assetid: cbaeb0e1-56b6-43b4-812a-596b2859c329
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 85e306a230d3e06330fd449f40bb001417ac9801
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55033152"
---
# <a name="ca2137-transparent-methods-must-contain-only-verifiable-il"></a>CA2137: Transparentní metody musí obsahovat pouze ověřitelné IL

|||
|-|-|
|TypeName|TransparentMethodsMustBeVerifiable|
|CheckId|CA2137|
|Kategorie|Microsoft.Security|
|Narušující změna|Narušující|

## <a name="cause"></a>Příčina
 Metoda obsahuje kód, který nelze ověřit, nebo vrací typ odkazem.

## <a name="rule-description"></a>Popis pravidla
 Toto pravidlo je vyvoláno při pokusech transparentního kódu zabezpečení spustit jazyk MSIL (Microsoft Intermediate Language), který nelze ověřit. Pravidlo však neobsahuje úplný ověřovatel jazyka IL a místo toho k zachycení většiny porušení ověření jazyka MSIL používá heuristiky.

 Ujistěte se, že váš kód obsahuje pouze ověřitelného kódu MSIL, spusťte [Peverify.exe (Nástroj PEVerify)](/dotnet/framework/tools/peverify-exe-peverify-tool) v sestavení. Spustit PEVerify s **/ transparentní** možnost, která omezí výstup na pouze neověřitelný transparentních metodách, které by způsobilo chybu. Pokud / není použita možnost transparentní, PEVerify také ověří kritické metody, které můžou obsahovat kód, který nelze ověřit.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, označte metody <xref:System.Security.SecurityCriticalAttribute> nebo <xref:System.Security.SecuritySafeCriticalAttribute> atribut, nebo odeberte neověřitelný kód.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo.

## <a name="example"></a>Příklad
 Metoda v tomto příkladu používá neověřitelný kód a by měly být označené <xref:System.Security.SecurityCriticalAttribute> nebo <xref:System.Security.SecuritySafeCriticalAttribute> atribut.

 [!code-csharp[FxCop.Security.CA2137.TransparentMethodsMustBeVerifiable#1](../code-quality/codesnippet/CSharp/ca2137-transparent-methods-must-contain-only-verifiable-il_1.cs)]