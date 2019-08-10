---
title: 'CA2139: Transparentní metody nemusí používat atribut HandleProcessCorruptingExceptions'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2139
ms.assetid: 45a0328a-add7-40f9-8934-dff59beb02b3
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f6808c5e9b5d35ab6ec8d4012f08e15cba9a159d
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68920569"
---
# <a name="ca2139-transparent-methods-may-not-use-the-handleprocesscorruptingexceptions-attribute"></a>CA2139: Transparentní metody nemusí používat atribut HandleProcessCorruptingExceptions

|||
|-|-|
|TypeName|TransparentMethodsMustNotHandleProcessCorruptingExceptions|
|CheckId|CA2139|
|Kategorie|Microsoft.Security|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
Transparentní metoda je označena <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute> atributem.

## <a name="rule-description"></a>Popis pravidla
Toto pravidlo aktivuje jakoukoliv metodu, která je transparentní a pokusí se zpracovat výjimku, která je poškozená <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute> , pomocí atributu. Výjimka poškození procesu je klasifikace výjimek verze 4,0, jako je například <xref:System.AccessViolationException>výjimka třídy CLR. Atribut HandleProcessCorruptedStateExceptionsAttribute lze použít pouze metodami kritickými pro bezpečnost a bude ignorován, je-li použit u transparentních metod. Aby bylo možné zpracovat výjimky poškozené procesem, tato metoda musí být kritická nebo zabezpečená zabezpečení.

## <a name="how-to-fix-violations"></a>Jak opravit porušení
Chcete-li opravit porušení tohoto pravidla, odeberte <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute> atribut nebo označte metodu <xref:System.Security.SecurityCriticalAttribute> <xref:System.Security.SecuritySafeCriticalAttribute> atributem nebo.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
Nepotlačujte upozornění na toto pravidlo.

## <a name="example"></a>Příklad
V tomto příkladu je průhledná metoda označena <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute> atributem a selže pravidlo. Metoda by měla být také označena <xref:System.Security.SecurityCriticalAttribute> <xref:System.Security.SecuritySafeCriticalAttribute> atributem nebo.

[!code-csharp[FxCop.Security.CA2139.TransparentMethodsMustNotHandleProcessCorruptingExceptions#1](../code-quality/codesnippet/CSharp/ca2139-transparent-methods-may-not-use-the-handleprocesscorruptingexceptions-attribute_1.cs)]