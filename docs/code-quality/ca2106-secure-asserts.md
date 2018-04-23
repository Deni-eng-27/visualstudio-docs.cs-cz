---
title: 'CA2106: Zabezpečte nepodmíněné výrazy'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2106
- SecureAsserts
helpviewer_keywords:
- CA2106
- SecureAsserts
ms.assetid: 91feb36e-6e2c-436c-8272-5aee31f77e98
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 40d497efd766fa5716b92e16ad513df85a41d2cf
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="ca2106-secure-asserts"></a>CA2106: Zabezpečte nepodmíněné výrazy
|||
|-|-|
|TypeName|SecureAsserts|
|CheckId|CA2106|
|Kategorie|Microsoft.Security|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Metoda uplatňuje oprávnění a na volajícím nejsou vykonány žádné kontroly zabezpečení.

## <a name="rule-description"></a>Popis pravidla
 Uplatnění oprávnění zabezpečení bez provedení jakékoliv kontroly zabezpečení může zanechat ve vašem kódu zneužitelné slabé stránky zabezpečení. Procházení zásobníku zabezpečení zastaví, když je uplatněna oprávnění zabezpečení. Pokud uplatňujete oprávnění bez provedení jakýchkoli kontrol na volajícího, může volající nepřímo spouštění kódu pomocí oprávnění. Vyhodnotí bez kontroly zabezpečení jsou přípustné pouze pokud jste si jisti, že assert nelze použít škodlivé způsobem. Assert je neškodné, pokud je kód, který zavoláte neškodné nebo uživatelé nemůžou projít libovolné informace do kódu, které můžete volat.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Opravit porušení toto pravidlo, přidejte metodu nebo jeho deklarující typ požadavek zabezpečení.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Potlačíte upozornění na toto pravidlo až po kontrolu pečlivě zabezpečení.

## <a name="see-also"></a>Viz také
 <xref:System.Security.CodeAccessPermission.Assert%2A?displayProperty=fullName> [Pokyny pro zabezpečené kódování](/dotnet/standard/security/secure-coding-guidelines)