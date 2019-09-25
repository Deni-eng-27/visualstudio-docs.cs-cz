---
title: 'CA1303: Nepředávejte literály jako lokalizované parametry'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- Do not pass literals as localized parameters
- DoNotPassLiteralsAsLocalizedParameters
- CA1303
helpviewer_keywords:
- DoNotPassLiteralsAsLocalizedParameters
- CA1303
ms.assetid: 904d284e-76d0-4b8f-a4df-0094de8d7aac
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 2700dc2ade7ba901f15f67045e3170e2bbb40ff8
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/24/2019
ms.locfileid: "71235119"
---
# <a name="ca1303-do-not-pass-literals-as-localized-parameters"></a>CA1303: Nepředávejte literály jako lokalizované parametry

|||
|-|-|
|TypeName|DoNotPassLiteralsAsLocalizedParameters|
|CheckId|CA1303|
|Kategorie|Microsoft.Globalization|
|Zásadní změna|Nenarušující|

## <a name="cause"></a>příčina

Metoda předává řetězcový literál jako parametr konstruktoru nebo metodě .NET a tento řetězec by měl být Lokalizovatelný.

Toto upozornění je vyvoláno, když je řetězcový literál předán jako hodnota parametru nebo vlastnosti a jeden nebo více z následujících případů je pravda:

- <xref:System.ComponentModel.LocalizableAttribute> Atribut parametru nebo vlastnosti je nastaven na hodnotu true.

- Název parametru nebo vlastnosti obsahuje text "text", "zpráva" nebo "titulek".

- Název řetězcového parametru, který je předán metodě Console. Write nebo Console. WriteLine, je buď hodnota, nebo formát.

## <a name="rule-description"></a>Popis pravidla

Řetězcové literály, které jsou vloženy ve zdrojovém kódu, je obtížné lokalizovat.

## <a name="how-to-fix-violations"></a>Jak opravit porušení

Chcete-li opravit porušení tohoto pravidla, nahraďte řetězcový literál řetězcem načteným prostřednictvím instance <xref:System.Resources.ResourceManager> třídy.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Je bezpečné potlačit upozornění z tohoto pravidla, pokud knihovna kódu nebude lokalizována nebo pokud řetězec není vystaven koncovému uživateli nebo vývojáři pomocí knihovny kódu.

Uživatelé mohou odstranit šum proti metodám, které by neměly být předány lokalizované řetězce buď přejmenováním parametru nebo vlastnosti, nebo označením těchto položek jako podmíněné.

## <a name="example"></a>Příklad

Následující příklad ukazuje metodu, která vyvolá výjimku, pokud některý z jejích dvou argumentů je mimo rozsah. Pro první argument je konstruktoru výjimky předán literální řetězec, který porušuje toto pravidlo. Pro druhý argument je konstruktor správně předán pomocí řetězce načteného prostřednictvím <xref:System.Resources.ResourceManager>.

[!code-cpp[FxCop.Globalization.DoNotPassLiterals#1](../code-quality/codesnippet/CPP/ca1303-do-not-pass-literals-as-localized-parameters_1.cpp)]
[!code-vb[FxCop.Globalization.DoNotPassLiterals#1](../code-quality/codesnippet/VisualBasic/ca1303-do-not-pass-literals-as-localized-parameters_1.vb)]
[!code-csharp[FxCop.Globalization.DoNotPassLiterals#1](../code-quality/codesnippet/CSharp/ca1303-do-not-pass-literals-as-localized-parameters_1.cs)]

## <a name="see-also"></a>Viz také:

- [Prostředky v aplikacích klasické pracovní plochy](/dotnet/framework/resources/index)