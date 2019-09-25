---
title: 'CA1305: Určete IFormatProvider'
ms.date: 06/30/2018
ms.topic: reference
f1_keywords:
- SpecifyIFormatProvider
- CA1305
helpviewer_keywords:
- CA1305
- SpecifyIFormatProvider
ms.assetid: fb34ed9a-4eab-47cc-8eef-3068a4a1397e
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- multiple
ms.openlocfilehash: a9f6c8fd44749de43d86bf8037df0130ad682321
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/24/2019
ms.locfileid: "71235038"
---
# <a name="ca1305-specify-iformatprovider"></a>CA1305: Určete IFormatProvider

|||
|-|-|
|TypeName|SpecifyIFormatProvider|
|CheckId|CA1305|
|Kategorie|Microsoft.Globalization|
|Zásadní změna|Nenarušující|

## <a name="cause"></a>příčina

Metoda nebo konstruktor volá jeden nebo více členů, které mají přetížení přijímající <xref:System.IFormatProvider?displayProperty=fullName> parametr, a metoda nebo konstruktor nevolá přetížení, které <xref:System.IFormatProvider> přijímá parametr.

Toto pravidlo ignoruje volání metod .NET, které jsou zdokumentovány jako ignorování <xref:System.IFormatProvider> parametru. Pravidlo také ignoruje následující metody:

- <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType>
- <xref:System.Resources.ResourceManager.GetObject%2A?displayProperty=nameWithType>
- <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=nameWithType>

## <a name="rule-description"></a>Popis pravidla

V případě, <xref:System.IFormatProvider> že objekt nebonenízadán,nemusímítvýchozíhodnota,kterájeposkytnutapřetíženýmčlenem,efekt,kterýchcetevevšechnárodníchprostředích.<xref:System.Globalization.CultureInfo?displayProperty=nameWithType> Kromě toho členové rozhraní .NET zvolí výchozí jazykovou verzi a formátování na základě předpokladů, které nemusí být pro váš kód správné. Chcete-li se ujistit, že kód funguje podle očekávání pro vaše scénáře, měli byste dodávat informace specifické pro jazykovou verzi podle následujících pokynů:

- Pokud se hodnota zobrazí uživateli, použijte aktuální jazykovou verzi. Viz <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType>.

- Pokud bude hodnota uložena a bude mít k dispozici software (uložený v souboru nebo databázi), použijte invariantní jazykovou verzi. Viz <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>.

- Pokud neznáte cíl hodnoty, je nutné, aby příjemce dat nebo poskytovatel tuto jazykovou verzi určil.

I v případě, že je výchozí chování přetíženého členu vhodné pro vaše potřeby, je lepší explicitně volat přetížení specifické pro jazykovou verzi, aby váš kód byl vlastní dokument a snadněji se udržoval.

## <a name="how-to-fix-violations"></a>Jak opravit porušení

Chcete-li opravit porušení tohoto pravidla, použijte přetížení, které přijímá <xref:System.IFormatProvider> argument. Nebo použijte [ C# interpolující řetězec](/dotnet/csharp/tutorials/string-interpolation) a předejte <xref:System.FormattableString.Invariant%2A?displayProperty=nameWithType> ho do metody.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Z tohoto pravidla je bezpečné potlačit upozornění, když je jisté, že výchozí formát je správný, a pokud je zachování kódu důležitou prioritou.

## <a name="example"></a>Příklad

V následujícím kódu `example1` řetězec porušuje CA1305 pravidla. Řetězec splňuje CA1305 pravidla předáním <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType>, který implementuje <xref:System.IFormatProvider>na <xref:System.String.Format(System.IFormatProvider,System.String,System.Object)?displayProperty=nameWithType>. `example2` Řetězec splňuje CA1305 pravidla předáním interpolované <xref:System.FormattableString.Invariant%2A?displayProperty=fullName]>řetězce. `example3`

```csharp
string name = "Georgette";

// Violates CA1305
string example1 = String.Format("Hello {0}", name);

// Satisfies CA1305
string example2 = String.Format(CultureInfo.CurrentCulture, "Hello {0}", name);

// Satisfies CA1305
string example3 = FormattableString.Invariant($"Hello {name}");
```

## <a name="related-rules"></a>Související pravidla

- [CA1304: Zadat CultureInfo](../code-quality/ca1304-specify-cultureinfo.md)

## <a name="see-also"></a>Viz také:

- [Použití třídy CultureInfo](/dotnet/standard/globalization-localization/globalization#work-with-culture-specific-settings)