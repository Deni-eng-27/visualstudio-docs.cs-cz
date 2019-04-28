---
title: 'CA1054: Parametry identifikátoru URI by neměly být řetězce'
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- CA1054
- UriParametersShouldNotBeStrings
helpviewer_keywords:
- CA1054
- UriParametersShouldNotBeStrings
ms.assetid: 8e99d72b-a658-47a7-8dd5-9784ce2c30b8
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 03d850eeb668f6c2b47d663b55e5461cabf9cbbf
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62784171"
---
# <a name="ca1054-uri-parameters-should-not-be-strings"></a>CA1054: Parametry identifikátoru URI by neměly být řetězce

|||
|-|-|
|TypeName|UriParametersShouldNotBeStrings|
|CheckId|CA1054|
|Kategorie|Microsoft.Design|
|Narušující změna|Narušující|

## <a name="cause"></a>Příčina

Typ deklaruje metodu s parametrem řetězec, jehož název obsahuje "uri", "Uri", "urn", "Urn", "url" nebo "Url" a typ nedeklaruje odpovídající přetížení přijímající <xref:System.Uri?displayProperty=fullName> parametru.

Ve výchozím nastavení, toto pravidlo pouze vypadá v externě viditelné typy, ale je to [konfigurovatelné](#configurability).

## <a name="rule-description"></a>Popis pravidla

Toto pravidlo rozdělí název parametru do tokenů podle konvence camelCase a zkontroluje, zda každý token se rovná "uri", "Uri", "urn", "Urn", "url" nebo "Url". Pokud se zjistí shoda, pravidlo předpokládá, že parametr představuje identifikátor URI (URI). Řetězcová reprezentace identifikátoru URI je náchylná k chybám analýzy a kódování a může vést k ohrožení bezpečnosti. Pakliže metoda přijímá řetězcovou reprezentaci identifikátoru URI, mělo by být odpovídající přetížení, poskytnuto, která přijímá instanci <xref:System.Uri> třídu, která poskytuje tyto služby bezpečným a zabezpečeným způsobem.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

Chcete-li opravit porušení tohoto pravidla, změňte parametr <xref:System.Uri> typu; to je zásadní změnu. Můžete také poskytovat přetížení metody, která přijímá <xref:System.Uri> parametr; jedná se o změnu pevné.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Je bezpečné potlačit upozornění tohoto pravidla, je-li parametr nepředstavuje identifikátor URI.

## <a name="configurability"></a>Možnosti konfigurace:

Pokud používáte systém toto pravidlo z [analyzátory FxCop](install-fxcop-analyzers.md) (a ne prostřednictvím statickou analýzu kódu), které části můžete nakonfigurovat vašeho základu kódu pro toto pravidlo spouštět, v závislosti na jejich přístupnost. Například k určení, že se má pravidlo spustit jenom na povrchu neveřejné rozhraní API, přidejte následující dvojice klíč hodnota do souboru .editorconfig ve vašem projektu:

```
dotnet_code_quality.ca1054.api_surface = private, internal
```

Tuto možnost pro právě toto pravidlo, všechna pravidla nebo pro všechna pravidla můžete konfigurovat v této kategorii (návrh). Další informace najdete v tématu [analyzátory FxCop konfigurace](configure-fxcop-analyzers.md).

## <a name="example"></a>Příklad

Následující příklad ukazuje typ, `ErrorProne`, který porušuje tato pravidla a typ, `SaferWay`, který splňuje pravidlo.

[!code-csharp[FxCop.Design.UriNotString#1](../code-quality/codesnippet/CSharp/ca1054-uri-parameters-should-not-be-strings_1.cs)]
[!code-vb[FxCop.Design.UriNotString#1](../code-quality/codesnippet/VisualBasic/ca1054-uri-parameters-should-not-be-strings_1.vb)]
[!code-cpp[FxCop.Design.UriNotString#1](../code-quality/codesnippet/CPP/ca1054-uri-parameters-should-not-be-strings_1.cpp)]

## <a name="related-rules"></a>Související pravidla

- [CA1056: Vlastnosti identifikátoru URI by neměly být řetězce](../code-quality/ca1056-uri-properties-should-not-be-strings.md)
- [CA1055: Identifikátor URI návratové hodnoty by neměly být řetězce](../code-quality/ca1055-uri-return-values-should-not-be-strings.md)
- [CA2234: Předejte objekty System.Uri namísto řetězců](../code-quality/ca2234-pass-system-uri-objects-instead-of-strings.md)
- [CA1057: Volání řetězcové přetížení identifikátoru URI volá přetížení System.Uri](../code-quality/ca1057-string-uri-overloads-call-system-uri-overloads.md)