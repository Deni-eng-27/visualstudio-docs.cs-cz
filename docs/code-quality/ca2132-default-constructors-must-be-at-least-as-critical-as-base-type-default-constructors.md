---
title: 'CA2132: Výchozí konstruktory nesmějí být méně kritické než výchozí konstruktory základního typu'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2132
ms.assetid: e758afa1-8bde-442a-8a0a-bd1ea7b0ce4d
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c0d878fb51625ff9a56fcf70c6ebbbe661dc2abb
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="ca2132-default-constructors-must-be-at-least-as-critical-as-base-type-default-constructors"></a>CA2132: Výchozí konstruktory nesmějí být méně kritické než výchozí konstruktory základního typu
|||
|-|-|
|TypeName|DefaultConstructorsMustHaveConsistentTransparency|
|CheckId|CA2132|
|Kategorie|Microsoft.Security|
|Narušující změna|Narušující|

> [!NOTE]
>  Toto upozornění se použije pouze na kód, který běží CoreCLR (verze modulu CLR, které jsou specifické pro Silverlight webových aplikací).

## <a name="cause"></a>příčina
 Atribut průhlednost výchozího konstruktoru odvozené třídy není kritické průhlednost základní třídy.

## <a name="rule-description"></a>Popis pravidla
 Typy a členy, kteří mají <xref:System.Security.SecurityCriticalAttribute> nelze použít kód aplikace Silverlight. Typy a členy kritické z hlediska zabezpečení lze použít pouze prostřednictvím důvěryhodného kódu v knihovně tříd rozhraní .NET Framework aplikace Silverlight. Protože veřejné nebo chráněné konstrukce v odvozené třídě musí mít stejnou nebo větší transparentnost než jejich základní třída, nelze třídu v aplikaci odvodit z třídy označené jako SecurityCritical.

 Pro CoreCLR kódu platformy Pokud základní typ veřejných nebo chráněného neprůhledný výchozí konstruktor pak odvozený typ musí orientují výchozí konstruktor dědičnosti pravidla. Odvozený typ musí také mít výchozí konstruktor a tento konstruktor musí být alespoň tak důležité výchozí konstruktor základního typu.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení zásady, odebrat typ nebo není odvozena od neprůhledný typ zabezpečení.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Není potlačení upozornění od tohoto pravidla. Porušení toto pravidlo kód aplikace bude mít za následek CoreCLR odmítá se načíst typ s <xref:System.TypeLoadException>.

### <a name="code"></a>Kód
 [!code-csharp[FxCop.Security.CA2132.DefaultConstructorsMustHaveConsistentTransparency#1](../code-quality/codesnippet/CSharp/ca2132-default-constructors-must-be-at-least-as-critical-as-base-type-default-constructors_1.cs)]

### <a name="comments"></a>Komentáře