---
title: 'CA2108: Revize deklarativních zabezpečení na hodnotách'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- ReviewDeclarativeSecurityOnValueTypes
- CA2108
helpviewer_keywords:
- ReviewDeclarativeSecurityOnValueTypes
- CA2108
ms.assetid: d62bffdd-3826-4d52-a708-1c646c5d48c2
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c62704a99e5952c313c4ba11a71fd234070d6df8
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53882231"
---
# <a name="ca2108-review-declarative-security-on-value-types"></a>CA2108: Revize deklarativních zabezpečení na hodnotách

|||
|-|-|
|TypeName|ReviewDeclarativeSecurityOnValueTypes|
|CheckId|CA2108|
|Kategorie|Microsoft.Security|
|Narušující změna|Pevné|

## <a name="cause"></a>příčina

Veřejný nebo chráněný hodnotový typ je zabezpečen pomocí [Data a modelování](/dotnet/framework/data/index) nebo [požadavky propojení](/dotnet/framework/misc/link-demands).

## <a name="rule-description"></a>Popis pravidla

Typy hodnot jsou přiděleny a inicializován pomocí jejich výchozí konstruktory před další konstruktory. Pokud hodnota typ je zabezpečen pomocí s požadavkem nebo LinkDemand a volající nemá oprávnění, které splňují kontrola zabezpečení, některý konstruktor jiné než výchozí hodnota se nezdaří a bude vyvolána výjimka zabezpečení. Typ hodnoty není uvolněný; je ponechána ve stavu, nastavte jeho výchozí konstruktor. Nepředpokládejte, že volající, který předá instance typu hodnoty má oprávnění k vytváření a přístup k instanci.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

Pokud odeberete z typu kontroly zabezpečení a použití zabezpečení na úrovni metoda zkontroluje místo něj nelze opravit porušení tohoto pravidla. Oprava porušení tímto způsobem nezabrání volajícím s nedostatečná oprávnění od získání instance typu hodnoty. Ujistěte se, že instance typu hodnoty ve svém výchozím stavu není zveřejnit citlivé informace a nelze použít škodlivých způsobem.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Upozornění tohoto pravidla můžete potlačit, pokud jakýkoli volající můžete získat instance typu hodnoty ve svém výchozím stavu bez představující ohrožení zabezpečení.

## <a name="example-1"></a>Příklad 1

Následující příklad ukazuje knihovnu obsahující hodnotový typ, který porušuje tato pravidla. `StructureManager` Typ předpokládá, že volající, který předá instance typu hodnoty má oprávnění k vytváření a přístup k instanci.

[!code-csharp[FxCop.Security.DemandOnValueType#1](../code-quality/codesnippet/CSharp/ca2108-review-declarative-security-on-value-types_1.cs)]

## <a name="example-2"></a>Příklad 2

Následující aplikace ukazuje slabé stránky knihovny.

[!code-csharp[FxCop.Security.TestDemandOnValueType#1](../code-quality/codesnippet/CSharp/ca2108-review-declarative-security-on-value-types_2.cs)]

Tento příklad vytvoří následující výstup:

```txt
Structure custom constructor: Request failed.
New values SecuredTypeStructure 100 100
New values SecuredTypeStructure 200 200
```

## <a name="see-also"></a>Viz také:

- [Požadavky propojení](/dotnet/framework/misc/link-demands)
- [Data a modelování](/dotnet/framework/data/index)
