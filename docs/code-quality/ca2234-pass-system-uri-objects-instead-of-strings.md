---
title: 'CA2234: Předejte objekty System.Uri namísto řetězců'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- PassSystemUriObjectsInsteadOfStrings
- CA2234
helpviewer_keywords:
- CA2234
- PassSystemUriObjectsInsteadOfStrings
ms.assetid: 14616b37-74c4-4286-b051-115d00aceb5f
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: acaed774bbfc797bf5171bfabeb2febbbf37a391
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53916585"
---
# <a name="ca2234-pass-systemuri-objects-instead-of-strings"></a>CA2234: Předejte objekty System.Uri namísto řetězců

|||
|-|-|
|TypeName|PassSystemUriObjectsInsteadOfStrings|
|CheckId|CA2234|
|Kategorie|Microsoft.Usage|
|Narušující změna|Pevné|

## <a name="cause"></a>příčina
 Je provedeno volání metody, která má řetězcový parametr, jehož název obsahuje "uri", "Uri", "urn", "Urn", "url" nebo "Url"; a deklarující typ metody obsahuje odpovídající přetížení metody, která má <xref:System.Uri?displayProperty=fullName> parametru.

## <a name="rule-description"></a>Popis pravidla
 Název parametru je rozděleno na tokeny, které podle konvence camelCase a potom každý token se zkontroluje, jestli se rovná "uri", "Uri", "urn", "Urn", "url" nebo "Url". Pokud se zjistí shoda, parametr se předpokládá, že představují identifikátor URI (URI). Řetězcová reprezentace identifikátoru URI je náchylná k chybám analýzy a kódování a může vést k ohrožení bezpečnosti. <xref:System.Uri> Třída poskytuje tyto služby bezpečným a zabezpečeným způsobem. Pokud je možnost volby mezi dvě přetížení, které se liší pouze o reprezentaci identifikátoru URI, uživatel by měl vybrat přetížení přijímající <xref:System.Uri> argument.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, zavolejte přetížení přijímající <xref:System.Uri> argument.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Je bezpečné potlačit upozornění tohoto pravidla, je-li parametr řetězec nepředstavuje identifikátor URI.

## <a name="example"></a>Příklad
 Následující příklad ukazuje metodu, `ErrorProne`, který porušuje pravidla a metodu, `SaferWay`, která správně volá <xref:System.Uri> přetížení.

 [!code-vb[FxCop.Usage.PassUri#1](../code-quality/codesnippet/VisualBasic/ca2234-pass-system-uri-objects-instead-of-strings_1.vb)]
 [!code-cpp[FxCop.Usage.PassUri#1](../code-quality/codesnippet/CPP/ca2234-pass-system-uri-objects-instead-of-strings_1.cpp)]
 [!code-csharp[FxCop.Usage.PassUri#1](../code-quality/codesnippet/CSharp/ca2234-pass-system-uri-objects-instead-of-strings_1.cs)]

## <a name="related-rules"></a>Související pravidla
 [CA1057: Volání řetězcové přetížení identifikátoru URI volá přetížení System.Uri](../code-quality/ca1057-string-uri-overloads-call-system-uri-overloads.md)

 [CA1056: Vlastnosti identifikátoru URI by neměly být řetězce](../code-quality/ca1056-uri-properties-should-not-be-strings.md)

 [CA1054: Parametry identifikátoru URI by neměly být řetězce](../code-quality/ca1054-uri-parameters-should-not-be-strings.md)

 [CA1055: Identifikátor URI návratové hodnoty by neměly být řetězce](../code-quality/ca1055-uri-return-values-should-not-be-strings.md)