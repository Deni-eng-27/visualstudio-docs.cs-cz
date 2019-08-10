---
title: 'CA2114: Zabezpečení metod by mělo být nadmnožinou typu'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- MethodSecurityShouldBeASupersetOfType
- CA2114
helpviewer_keywords:
- CA2114
- MethodSecurityShouldBeASupersetOfType
ms.assetid: 663f7aa4-8be5-4bd5-be92-4e9444f07077
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d83da42a029d746899bfaccf5d62f8856a040611
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68921105"
---
# <a name="ca2114-method-security-should-be-a-superset-of-type"></a>CA2114: Zabezpečení metod by mělo být nadmnožinou typu

|||
|-|-|
|TypeName|MethodSecurityShouldBeASupersetOfType|
|CheckId|CA2114|
|Kategorie|Microsoft.Security|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
Typ má deklarativní zabezpečení a jedna z jeho metod má deklarativní zabezpečení pro stejnou akci zabezpečení a akce zabezpečení není [propojením požadavků](/dotnet/framework/misc/link-demands)a oprávnění kontrolovaného typem nejsou podmnožinou oprávnění zkontrolovaných metodou.

## <a name="rule-description"></a>Popis pravidla
Metoda by neměla mít deklarativní zabezpečení na úrovni metody i typu pro stejnou akci. Tyto dvě kontroly nejsou kombinovány. použije se jenom požadavek úrovně metody. Například pokud typ vyžaduje oprávnění `X`a jedna z jeho metod požaduje oprávnění `Y`, kód nemusí mít oprávnění `X` ke spuštění metody.

## <a name="how-to-fix-violations"></a>Jak opravit porušení
Zkontrolujte kód a ujistěte se, že jsou nutné obě akce. Pokud jsou požadovány obě akce, ujistěte se, že akce na úrovni metody zahrnuje zabezpečení specifikované na úrovni typu. Například pokud váš typ požaduje `X`oprávnění a jeho metoda musí také vyžadovat oprávnění `Y`, metoda by měla explicitně vyžadovat `X` a `Y`.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
V případě, že metoda nevyžaduje zabezpečení určené typem, je bezpečné potlačit upozornění od tohoto pravidla. Nejedná se ale o běžný scénář a může to znamenat, že je potřeba pečlivé přezkoumání návrhu.

## <a name="example-1"></a>Příklad 1

Následující příklad používá oprávnění prostředí k demonstraci nebezpečí porušení tohoto pravidla. V tomto příkladu kód aplikace vytvoří instanci zabezpečeného typu před odepřením oprávnění vyžadovaných typem. Ve scénáři reálného ohrožení vyžaduje aplikace další způsob, jak získat instanci objektu.

V následujícím příkladu Knihovna požaduje oprávnění k zápisu pro typ a oprávnění číst pro metodu.

[!code-csharp[FxCop.Security.MethodLevelSecurity#1](../code-quality/codesnippet/CSharp/ca2114-method-security-should-be-a-superset-of-type_1.cs)]

## <a name="example-2"></a>Příklad 2

Následující kód aplikace demonstruje ohrožení zabezpečení knihovny voláním metody, i když nesplňuje požadavek zabezpečení na úrovni typu.

[!code-csharp[FxCop.Security.TestMethodLevelSecurity#1](../code-quality/codesnippet/CSharp/ca2114-method-security-should-be-a-superset-of-type_2.cs)]

Tento příklad vytvoří následující výstup:

```txt
[All permissions] Personal information: 6/16/1964 12:00:00 AM
[No write permission (demanded by type)] Personal information: 6/16/1964 12:00:00 AM
[No read permission (demanded by method)] Could not access personal information: Request failed.
```

## <a name="see-also"></a>Viz také:

- [Pokyny pro zabezpečené kódování](/dotnet/standard/security/secure-coding-guidelines)
- [Požadavky propojení](/dotnet/framework/misc/link-demands)
- [Data a modelování](/dotnet/framework/data/index)