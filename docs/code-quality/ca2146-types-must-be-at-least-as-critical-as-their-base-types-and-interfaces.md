---
title: 'CA2146: Typy musí být alespoň tak kritické, jako jejich základní typy a rozhraní'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2146
ms.assetid: 241fb784-1f6b-46e5-8ceb-c438e341d38e
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a70e999505bd900a7b3d89693ef4f6a1cef9de7d
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68920428"
---
# <a name="ca2146-types-must-be-at-least-as-critical-as-their-base-types-and-interfaces"></a>CA2146: Typy musí být alespoň tak kritické, jako jejich základní typy a rozhraní

|||
|-|-|
|TypeName|TypesMustBeAtLeastAsCriticalAsBaseTypes|
|CheckId|CA2146|
|Kategorie|Microsoft.Security|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
Transparentní typ je odvozen z typu, který je <xref:System.Security.SecuritySafeCriticalAttribute> označen jako <xref:System.Security.SecurityCriticalAttribute>nebo, nebo typ <xref:System.Security.SecuritySafeCriticalAttribute> , který je označen atributem, je odvozen <xref:System.Security.SecurityCriticalAttribute> z typu, který je označen atributem.

## <a name="rule-description"></a>Popis pravidla
Toto pravidlo je vyvoláno, když má odvozený typ atribut transparentnosti zabezpečení, který není tak kritický jako jeho základní typ nebo implementované rozhraní. Pouze kritické typy lze odvodit z kritických základních typů nebo mohou implementovat kritická rozhraní a pouze kritické typy nebo bezpečně kritické typy mohou být odvozeny ze základních bezpečně kritických typů nebo mohou implementovat bezpečně kritická rozhraní. Porušení tohoto pravidla v důsledku <xref:System.TypeLoadException> transparentnosti úrovně 2 pro odvozený typ.

## <a name="how-to-fix-violations"></a>Jak opravit porušení
Chcete-li toto porušení opravit, označte odvozený nebo implementující typ s atributem transparentnosti, který je nejméně tak důležitý jako základní typ nebo rozhraní.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
Nepotlačujte upozornění na toto pravidlo.

## <a name="example"></a>Příklad
[!code-csharp[FxCop.Security.CA2146.TypesMustBeAtLeastAsCriticalAsBaseTypes#1](../code-quality/codesnippet/CSharp/ca2146-types-must-be-at-least-as-critical-as-their-base-types-and-interfaces_1.cs)]