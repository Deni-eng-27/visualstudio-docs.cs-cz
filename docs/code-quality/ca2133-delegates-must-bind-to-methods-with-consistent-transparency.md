---
title: 'CA2133: Delegáti musejí být připojeni k metodám s konzistentní transparentností'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2133
ms.assetid: a09672e2-63cb-4abd-9e8f-dff515e101ce
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 389de424c3d9e2cd0e12431e857983b267213f9c
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="ca2133-delegates-must-bind-to-methods-with-consistent-transparency"></a>CA2133: Delegáti musejí být připojeni k metodám s konzistentní transparentností
|||
|-|-|
|TypeName|DelegatesMustBindWithConsistentTransparency|
|CheckId|CA2133|
|Kategorie|Microsoft.Security|
|Narušující změna|Narušující|

> [!NOTE]
>  Toto upozornění se použije pouze na kód, který běží CoreCLR (verze modulu CLR, které jsou specifické pro Silverlight webových aplikací).

## <a name="cause"></a>příčina
 Toto upozornění se aktivuje na metodu, která sváže delegáta označené <xref:System.Security.SecurityCriticalAttribute> metodě průhledná nebo která je označena <xref:System.Security.SecuritySafeCriticalAttribute>. Upozornění je také vyvoláno na metodě, která vytvoří vazbu transparentního delegáta nebo bezpečně kritického delegáta na kritickou metodu.

## <a name="rule-description"></a>Popis pravidla
 Delegát typy a metody, které se vytvořit vazbu k musí být konzistentní transparentnost. Delegáti transparentní a kritická pouze může vytvořit vazbu k jiné metody průhledných nebo kritická. Podobně kritické delegáti může svázat jenom nejdůležitější metody. Tato vazba pravidla ujistěte se, že pouze kód, který lze vyvolat metodu prostřednictvím delegáta může mít také vyvolat stejnou metodu přímo. Například pravidla vazby zabránit kód transparentní pro volání kód kritický pro přímo prostřednictvím transparentní delegáta.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Opravit porušení toto upozornění, změňte průhlednost delegáta nebo metody, která se váže tak, aby průhlednost dva jsou ekvivalentní.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo.

### <a name="code"></a>Kód
 [!code-csharp[FxCop.Security.CA2133.DelegatesMustBindWithConsistentTransparency#1](../code-quality/codesnippet/CSharp/ca2133-delegates-must-bind-to-methods-with-consistent-transparency_1.cs)]