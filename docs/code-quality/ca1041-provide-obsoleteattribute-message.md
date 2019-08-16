---
title: 'CA1041: Poskytněte zprávu ObsoleteAttribute'
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- CA1041
- ProvideObsoleteAttributeMessage
helpviewer_keywords:
- ProvideObsoleteAttributeMessage
- CA1041
ms.assetid: be5bee69-d2d2-44e1-be2e-3ea451969003
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: a0545503b80e2f256593012e06cdf7ccd8b3b5b1
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/16/2019
ms.locfileid: "69547641"
---
# <a name="ca1041-provide-obsoleteattribute-message"></a>CA1041: Poskytněte zprávu ObsoleteAttribute

|||
|-|-|
|TypeName|ProvideObsoleteAttributeMessage|
|CheckId|CA1041|
|Kategorie|Microsoft.Design|
|Narušující změna|Nenarušující|

## <a name="cause"></a>příčina

Typ nebo člen je označen pomocí <xref:System.ObsoleteAttribute?displayProperty=fullName> atributu, který <xref:System.ObsoleteAttribute.Message%2A?displayProperty=fullName> nemá zadanou vlastnost.

Ve výchozím nastavení toto pravidlo vyhledává pouze externě viditelné typy a členy, ale je možné jej [nakonfigurovat](#configurability).

## <a name="rule-description"></a>Popis pravidla

<xref:System.ObsoleteAttribute>slouží k označení zastaralých typů a členů knihovny. Příjemci knihovny by se měli vyhnout použití libovolného typu nebo člena, který je označený jako zastaralý. Důvodem je to, že nemusí být podporován a nakonec bude odebrán z novějších verzí knihovny. Je-li typ nebo člen označený pomocí <xref:System.ObsoleteAttribute> je zkompilován <xref:System.ObsoleteAttribute.Message%2A> , je zobrazena vlastnost atributu. To uživateli poskytuje informace o zastaralém typu nebo členu. Tyto informace obecně zahrnují, jak dlouho bude zastaralý typ nebo člen podporovaný Návrháři knihovny a upřednostňovanou náhradou, která se má použít.

## <a name="how-to-fix-violations"></a>Jak opravit porušení

Chcete-li opravit porušení tohoto pravidla, přidejte `message` parametr <xref:System.ObsoleteAttribute> do konstruktoru.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Potlačí upozornění z tohoto pravidla, <xref:System.ObsoleteAttribute.Message%2A> protože vlastnost poskytuje kritické informace o zastaralém typu nebo členu.

## <a name="configurability"></a>Konfigurovatelnost

Pokud toto pravidlo spouštíte z [analyzátorů FxCop](install-fxcop-analyzers.md) (a ne pomocí starší verze analýzy), můžete nakonfigurovat, které části základu kódu mají spustit toto pravidlo, na základě jejich přístupnosti. Například chcete-li určit, že pravidlo by mělo běžet pouze proti neveřejnému povrchu rozhraní API, přidejte do souboru. editorconfig v projektu následující dvojici klíč-hodnota:

```ini
dotnet_code_quality.ca1041.api_surface = private, internal
```

Tuto možnost můžete nakonfigurovat jenom pro toto pravidlo, pro všechna pravidla nebo pro všechna pravidla v této kategorii (návrh). Další informace najdete v tématu [Konfigurace analyzátorů FxCop](configure-fxcop-analyzers.md).

## <a name="example"></a>Příklad

Následující příklad ukazuje zastaralý člen, který má správně deklarovaný <xref:System.ObsoleteAttribute>.

[!code-cpp[FxCop.Design.ObsoleteAttributeOnMember#1](../code-quality/codesnippet/CPP/ca1041-provide-obsoleteattribute-message_1.cpp)]
[!code-csharp[FxCop.Design.ObsoleteAttributeOnMember#1](../code-quality/codesnippet/CSharp/ca1041-provide-obsoleteattribute-message_1.cs)]
[!code-vb[FxCop.Design.ObsoleteAttributeOnMember#1](../code-quality/codesnippet/VisualBasic/ca1041-provide-obsoleteattribute-message_1.vb)]

## <a name="see-also"></a>Viz také:

- <xref:System.ObsoleteAttribute?displayProperty=fullName>