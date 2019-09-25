---
title: 'CA2133: Delegáti musí mít vazbu s metodami s konzistentní transparentností'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2133
ms.assetid: a09672e2-63cb-4abd-9e8f-dff515e101ce
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 14061c0f54593a2cb9b591d39cb46a433b0e34be
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/24/2019
ms.locfileid: "71232313"
---
# <a name="ca2133-delegates-must-bind-to-methods-with-consistent-transparency"></a>CA2133: Delegáti musí mít vazbu s metodami s konzistentní transparentností

|||
|-|-|
|TypeName|DelegatesMustBindWithConsistentTransparency|
|CheckId|CA2133|
|Kategorie|Microsoft.Security|
|Zásadní změna|Narušující|

> [!NOTE]
> Toto upozornění je použito pouze pro kód, na kterém je spuštěn CoreCLR (verze modulu CLR, která je specifická pro webové aplikace Silverlight).

## <a name="cause"></a>příčina

Toto upozornění se aktivuje u metody, která váže delegáta, který je označený <xref:System.Security.SecurityCriticalAttribute> na metodu, která je průhledná nebo která je označena <xref:System.Security.SecuritySafeCriticalAttribute>atributem. Upozornění je také vyvoláno na metodě, která vytvoří vazbu transparentního delegáta nebo bezpečně kritického delegáta na kritickou metodu.

## <a name="rule-description"></a>Popis pravidla

Typy delegátů a metody, které jsou vázány na, musí mít konzistentní transparentnost. Transparentní a bezpečně kritické delegáti mohou být vázáni pouze na jiné transparentní nebo bezpečné metody kritické. Podobně, kritické delegáti mohou být vázáni pouze na kritické metody. Tato pravidla vazby zajišťují, že jediný kód, který může vyvolat metodu prostřednictvím delegáta, by mohl také vyvolat stejnou metodu přímo. Například pravidla vazby zabraňují transparentnímu kódu ve volání kritického kódu přímo prostřednictvím transparentního delegáta.

## <a name="how-to-fix-violations"></a>Jak opravit porušení

Chcete-li opravit porušení tohoto upozornění, změňte průhlednost delegáta nebo metody, kterou sváže, aby transparentnost těchto dvou je ekvivalentní.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Nepotlačujte upozornění na toto pravidlo.

### <a name="code"></a>Kód

[!code-csharp[FxCop.Security.CA2133.DelegatesMustBindWithConsistentTransparency#1](../code-quality/codesnippet/CSharp/ca2133-delegates-must-bind-to-methods-with-consistent-transparency_1.cs)]