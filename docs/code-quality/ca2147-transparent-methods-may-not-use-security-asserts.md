---
title: 'CA2147: Transparentní metody nemusí používat kontrolní příkazy zabezpečení'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- SecurityTransparentCodeShouldNotAssert
- CA2147
- CA2128
helpviewer_keywords:
- CA2128
- SecurityTransparentCodeShouldNotAssert
ms.assetid: 5d31e940-e599-4b23-9b28-1c336f8d910e
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e1b56001f5a083317911edde9282b66758deb1b6
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68920719"
---
# <a name="ca2147-transparent-methods-may-not-use-security-asserts"></a>CA2147: Transparentní metody nemusí používat kontrolní příkazy zabezpečení

|||
|-|-|
|TypeName|SecurityTransparentCodeShouldNotAssert|
|CheckId|CA2147|
|Kategorie|Microsoft.Security|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
Kód, který je označen <xref:System.Security.SecurityTransparentAttribute> jako, nemá udělena dostatečná oprávnění k vyhodnocení.

## <a name="rule-description"></a>Popis pravidla
Toto pravidlo analyzuje všechny metody a typy v sestavení, které je buď 100% transparentní, nebo smíšené transparentní/kritické, a označí jakékoli deklarativní nebo imperativní použití <xref:System.Security.CodeAccessPermission.Assert%2A>.

V době běhu <xref:System.Security.CodeAccessPermission.Assert%2A> <xref:System.InvalidOperationException> způsobí volání z transparentního kódu vyvolání. K této chybě může dojít v transparentním sestavení 100% a také ve smíšených transparentních/kritických sestaveních, kde je metoda nebo typ deklarována jako průhledná, ale obsahuje deklarativní nebo imperativní vyhodnocení.

.NET Framework 2,0 zavedl funkci s názvem *transparentnost*. Jednotlivé metody, pole, rozhraní, třídy a typy mohou být buď transparentní, nebo kritické.

Transparentní kód nemá povoleno zvyšovat oprávnění zabezpečení. Proto všechna oprávnění, která jsou udělena nebo vyřízená, jsou automaticky předána prostřednictvím kódu volající nebo hostitelské doméně aplikace. Příklady zvýšení oprávnění zahrnují výrazy, LinkDemand, SuppressUnmanagedCode a `unsafe` Code.

## <a name="how-to-fix-violations"></a>Jak opravit porušení
Chcete-li tento problém vyřešit, buď označte kód, který volá kontrolní výraz <xref:System.Security.SecurityCriticalAttribute>s, nebo odeberte Assert.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
Potlačit zprávu od tohoto pravidla.

## <a name="example"></a>Příklad
Pokud `SecurityTestClass` `Assert` metoda vyvolá výjimku<xref:System.InvalidOperationException>, tento kód se nezdaří, pokud je transparentní.

[!code-csharp[FxCop.Security.CA2147.TransparentMethodsMustNotUseSecurityAsserts#1](../code-quality/codesnippet/CSharp/ca2147-transparent-methods-may-not-use-security-asserts_1.cs)]

## <a name="example"></a>Příklad
Jednou z možností je revize kódu v níže uvedeném příkladu metoda SecurityTransparentMethod a pokud je metoda považována za bezpečnou ke zvýšení oprávnění, označit SecurityTransparentMethod se zabezpečeným zabezpečením. To vyžaduje, aby bylo provedeno podrobné, úplné a bezplatná audit zabezpečení pro metodu spolu s případnými voláními, ke kterým dojde v rámci metody v rámci kontrolního výrazu:

[!code-csharp[FxCop.Security.SecurityTransparentCode2#1](../code-quality/codesnippet/CSharp/ca2147-transparent-methods-may-not-use-security-asserts_2.cs)]

Další možností je odebrat z kódu kontrolní výraz a nechat libovolné následné oprávnění v/v souboru, které vyžaduje tok nad rámec SecurityTransparentMethod k volajícímu. To umožňuje kontroly zabezpečení. V takovém případě není nutné provádět audit zabezpečení, protože požadavky oprávnění budou předávány volajícímu nebo doméně aplikace. Požadavky na oprávnění jsou úzce řízeny prostřednictvím zásad zabezpečení, hostitelského prostředí a udělení oprávnění ke zdroji kódu.

## <a name="see-also"></a>Viz také:
[Upozornění zabezpečení](../code-quality/security-warnings.md)