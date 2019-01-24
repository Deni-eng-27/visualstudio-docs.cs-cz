---
title: 'CA1815: Přepište rovná se a operátor rovnosti na hodnotových typech | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1815
- OverrideEqualsAndOperatorEqualsOnValueTypes
helpviewer_keywords:
- OverrideEqualsAndOperatorEqualsOnValueTypes
- CA1815
ms.assetid: 0a8ab3a3-ee8e-46f7-985d-dcf00c89363b
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: e21585a7a56fde2fb46ea86adde92eecfd1a4565
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54785107"
---
# <a name="ca1815-override-equals-and-operator-equals-on-value-types"></a>CA1815: Přepište rovnosti a operátory rovnosti u typů hodnot
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|OverrideEqualsAndOperatorEqualsOnValueTypes|
|CheckId|CA1815|
|Kategorie|Microsoft.Performance|
|Narušující změna|Nenarušující|

## <a name="cause"></a>Příčina
 Veřejné hodnotový typ nemůže přepsat <xref:System.Object.Equals%2A?displayProperty=fullName>, nebo neimplementuje operátor rovnosti (==). Toto pravidlo nekontroluje výčty.

## <a name="rule-description"></a>Popis pravidla
 U typů hodnot, zděděná implementace metody <xref:System.Object.Equals%2A> používá knihovnu reflexe a porovnává obsah všech polí. Reflexe je výpočetně náročná a porovnání rovnosti všech polí může být zbytečné. Pokud budou uživatelé k porovnání nebo řazení instance nebo používají jako klíče zatřiďovací tabulky, typ hodnoty by měly implementovat <xref:System.Object.Equals%2A>. Pokud svůj oblíbený programovací jazyk podporuje přetížení operátoru, měli byste také poskytnout implementaci pro operátory rovnosti a nerovnosti.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, zajišťovat implementaci rozhraní <xref:System.Object.Equals%2A>. Pokud je to možné, implementujte operátor rovnosti.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Je bezpečné potlačit upozornění tohoto pravidla, pokud instance typu hodnoty nebudou porovnány, k sobě navzájem.

## <a name="example-of-a-violation"></a>Příkladem porušení

### <a name="description"></a>Popis
 Následující příklad ukazuje strukturu (typ hodnoty), který porušuje tato pravidla.

### <a name="code"></a>Kód
 [!code-csharp[FxCop.Performance.OverrideEqualsViolation#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Performance.OverrideEqualsViolation/cs/FxCop.Performance.OverrideEqualsViolation.cs#1)]

## <a name="example-of-how-to-fix"></a>Příklad, jak k opravě

### <a name="description"></a>Popis
 Následující příklad opravuje předchozí porušení tak, že přepíšete <xref:System.ValueType.Equals%2A?displayProperty=fullName> a implementace operátory rovnosti (==,! =).

### <a name="code"></a>Kód
 [!code-csharp[FxCop.Performance.OverrideEqualsFixed#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Performance.OverrideEqualsFixed/cs/FxCop.Performance.OverrideEqualsFixed.cs#1)]

## <a name="related-rules"></a>Související pravidla
 [CA2224: Přepište equals při přetížení operátoru rovnosti](../code-quality/ca2224-override-equals-on-overloading-operator-equals.md)

 [CA2231: Přetižte operátor equals při přepsání ValueType.Equals](../code-quality/ca2231-overload-operator-equals-on-overriding-valuetype-equals.md)

 [CA2226: Operátory by měly mít symetrické přetížení](../code-quality/ca2226-operators-should-have-symmetrical-overloads.md)

## <a name="see-also"></a>Viz také
 <xref:System.Object.Equals%2A?displayProperty=fullName>
