---
title: 'CA1306: Nastavte národního prostředí pro datové typy'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1306
- SetLocaleForDataTypes
helpviewer_keywords:
- CA1306
- SetLocaleForDataTypes
ms.assetid: 104297b2-5806-4de0-a8d9-c589380a796c
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c7bbb625554b64aa0a171ccf49b1ff9b40e771a5
ms.sourcegitcommit: 485ffaedb1ade71490f11cf05962add1718945cc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/16/2019
ms.locfileid: "72444339"
---
# <a name="ca1306-set-locale-for-data-types"></a>CA1306: Nastavte národního prostředí pro datové typy

|||
|-|-|
|TypeName|SetLocaleForDataTypes|
|CheckId|CA1306|
|Kategorie|Microsoft. Globalization|
|Zásadní změna|Nenarušující|

## <a name="cause"></a>příčina
Metoda nebo konstruktor vytvořila jednu nebo více instancí <xref:System.Data.DataTable?displayProperty=fullName> nebo <xref:System.Data.DataSet?displayProperty=fullName> a neexplicitně nastavila vlastnost locale (<xref:System.Data.DataTable.Locale%2A?displayProperty=fullName> nebo <xref:System.Data.DataSet.Locale%2A?displayProperty=fullName>).

## <a name="rule-description"></a>Popis pravidla
Národní prostředí Určuje prvky prezentace specifické pro jazykovou verzi pro data, jako je například formátování používané pro číselné hodnoty, symboly měny a pořadí řazení. Když vytvoříte <xref:System.Data.DataTable> nebo <xref:System.Data.DataSet>, měli byste nastavit národní prostředí explicitně. Ve výchozím nastavení je národní prostředí pro tyto typy aktuální jazyková verze. Pro data, která jsou uložena v databázi nebo souboru a jsou sdíleny globálně, by mělo být národní prostředí obvykle nastaveno na invariantní jazykovou verzi (<xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName>). Když jsou data sdílena napříč kulturami, použití výchozího národního prostředí může způsobit, že se obsah <xref:System.Data.DataTable> nebo <xref:System.Data.DataSet> zobrazí nebo nesprávně interpretuje.

## <a name="how-to-fix-violations"></a>Jak opravit porušení
Chcete-li opravit porušení tohoto pravidla, explicitně nastavte národní prostředí pro <xref:System.Data.DataTable> nebo <xref:System.Data.DataSet>.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
Z tohoto pravidla je bezpečné potlačit upozornění, když je knihovna nebo aplikace určena pro omezené místní cílové skupiny, data nejsou sdílena nebo výchozí nastavení vydává požadované chování ve všech podporovaných scénářích.

## <a name="example"></a>Příklad
Následující příklad vytvoří dvě instance <xref:System.Data.DataTable>.

[!code-csharp[FxCop.Globalization.DataTable#1](../code-quality/codesnippet/CSharp/ca1306-set-locale-for-data-types_1.cs)]

## <a name="see-also"></a>Viz také:

- <xref:System.Data.DataTable?displayProperty=fullName>
- <xref:System.Data.DataSet?displayProperty=fullName>
- <xref:System.Globalization.CultureInfo?displayProperty=fullName>
- <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName>
- <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName>
