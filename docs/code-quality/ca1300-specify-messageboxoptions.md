---
title: 'CA1300: Určete MessageBoxOptions'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- SpecifyMessageBoxOptions
- CA1300
helpviewer_keywords:
- SpecifyMessageBoxOptions
- CA1300
ms.assetid: 9357a724-026e-4a3d-a03a-f14635064ec6
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 746475e60bbe72c4ebfc51f13d0b2d4d0552ff62
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/24/2019
ms.locfileid: "71235197"
---
# <a name="ca1300-specify-messageboxoptions"></a>CA1300: Určete MessageBoxOptions

|||
|-|-|
|TypeName|SpecifyMessageBoxOptions|
|CheckId|CA1300|
|Kategorie|Microsoft.Globalization|
|Zásadní změna|Nenarušující|

## <a name="cause"></a>příčina

Metoda volá přetížení <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=fullName> metody, která <xref:System.Windows.Forms.MessageBoxOptions?displayProperty=fullName> nepřijímá argument.

## <a name="rule-description"></a>Popis pravidla

Chcete-li zobrazit okno se zprávou pro jazykové verze, které používají pořadí čtení zprava doleva, předejte do <xref:System.Windows.Forms.MessageBox.Show%2A> metody pole [MessageBoxOptions. RightAlign](<xref:System.Windows.Forms.MessageBoxOptions.RightAlign>) a [MessageBoxOptions. RtlReading](<xref:System.Windows.Forms.MessageBoxOptions.RtlReading>) . <xref:System.Windows.Forms.Control.RightToLeft%2A?displayProperty=fullName> Zkontrolujte vlastnost obsahujícího ovládacího prvku, abyste zjistili, jestli chcete použít směr čtení zprava doleva.

## <a name="how-to-fix-violations"></a>Jak opravit porušení

Chcete-li opravit porušení tohoto pravidla, zavolejte přetížení <xref:System.Windows.Forms.MessageBox.Show%2A> metody, která <xref:System.Windows.Forms.MessageBoxOptions> přijímá argument.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Je bezpečné potlačit upozornění z tohoto pravidla, pokud knihovna kódu nebude lokalizována do jazykové verze, která používá pořadí čtení zprava doleva.

## <a name="example"></a>Příklad

Následující příklad ukazuje metodu, která zobrazí okno se zprávou s možnostmi, které jsou vhodné pro pořadí čtení jazykové verze. Soubor prostředků, který není zobrazen, je požadován k sestavení příkladu. Použijte komentáře v příkladu k sestavení příkladu bez souboru prostředků a k otestování funkce zprava doleva.

[!code-vb[FxCop.Globalization.SpecifyMBOptions#1](../code-quality/codesnippet/VisualBasic/ca1300-specify-messageboxoptions_1.vb)]
[!code-csharp[FxCop.Globalization.SpecifyMBOptions#1](../code-quality/codesnippet/CSharp/ca1300-specify-messageboxoptions_1.cs)]

## <a name="see-also"></a>Viz také:

- <xref:System.Resources.ResourceManager?displayProperty=fullName>
- [Prostředky v aplikacích klasické pracovní plochy (.NET Framework)](/dotnet/framework/resources/index)