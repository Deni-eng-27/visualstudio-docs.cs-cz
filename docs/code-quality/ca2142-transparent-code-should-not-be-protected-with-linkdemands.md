---
title: 'CA2142: Transparentní kód by neměl být chráněn pomocí LinkDemands'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2142
ms.assetid: 6dc59053-5dd9-4583-bf10-5f339107e59f
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ab0f6aaae97a510b0521e10ad607a86988c345a3
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/24/2019
ms.locfileid: "71232086"
---
# <a name="ca2142-transparent-code-should-not-be-protected-with-linkdemands"></a>CA2142: Transparentní kód by neměl být chráněn pomocí LinkDemands

|||
|-|-|
|TypeName|TransparentMethodsShouldNotBeProtectedWithLinkDemands|
|CheckId|CA2142|
|Kategorie|Microsoft.Security|
|Zásadní změna|Narušující|

## <a name="cause"></a>příčina
Transparentní metoda vyžaduje nebo jiné <xref:System.Security.Permissions.SecurityAction> požadavky na zabezpečení.

## <a name="rule-description"></a>Popis pravidla
Toto pravidlo je vyvoláno transparentními metodami, které pro přístup k nim vyžadují LinkDemand. Kód transparentní z hlediska zabezpečení by neměl být odpovědný za ověření zabezpečení operace, a proto by neměl požadovat oprávnění. Vzhledem k tomu, že transparentní metody by měly být z důvodu zabezpečení neutrální, neměli byste provádět žádná bezpečnostní rozhodnutí. Navíc bezpečný kritický kód, který provádí rozhodnutí o zabezpečení, by neměl být závislý na transparentním kódu, aby byl takovým rozhodnutím dříve proveden.

## <a name="how-to-fix-violations"></a>Jak opravit porušení
Chcete-li opravit porušení tohoto pravidla, odeberte požadavek propojení na transparentní metodě nebo označte metodu <xref:System.Security.SecuritySafeCriticalAttribute> atributem, pokud provádí kontroly zabezpečení, jako třeba požadavky na zabezpečení.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
Nepotlačujte upozornění na toto pravidlo.

## <a name="example"></a>Příklad
V následujícím příkladu je pravidlo aktivováno pro metodu, protože metoda je transparentní a je označena pomocí LinkDemand <xref:System.Security.PermissionSet> , který <xref:System.Security.Permissions.SecurityAction>obsahuje.

[!code-csharp[FxCop.Security.CA2142.TransparentMethodsShouldNotBeProtectedWithLinkDemands#1](../code-quality/codesnippet/CSharp/ca2142-transparent-code-should-not-be-protected-with-linkdemands_1.cs)]

Nepotlačujte upozornění na toto pravidlo.