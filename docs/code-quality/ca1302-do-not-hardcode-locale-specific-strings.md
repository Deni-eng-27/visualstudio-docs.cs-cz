---
title: 'CA1302: Nekódujte pevně řetězce závislé národní prostředí'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- DoNotHardcodeLocaleSpecificStrings
- CA1302
helpviewer_keywords:
- DoNotHardcodeLocaleSpecificStrings
- CA1302
ms.assetid: 05ed134a-837d-43d7-bf97-906edeac44ce
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: b05f1aa31a38ff4f8e707d53d062abe3d10617fd
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53827725"
---
# <a name="ca1302-do-not-hardcode-locale-specific-strings"></a>CA1302: Nekódujte pevně řetězce závislé národní prostředí

|||
|-|-|
|TypeName|DoNotHardcodeLocaleSpecificStrings|
|CheckId|CA1302|
|Kategorie|Microsoft.Globalization|
|Narušující změna|Nenarušující|

## <a name="cause"></a>příčina
 Metoda používá řetězcový literál, který představuje část cesty k určitým složkám systému.

## <a name="rule-description"></a>Popis pravidla
 <xref:System.Environment.SpecialFolder?displayProperty=fullName> Výčet obsahuje členy, které odkazují na speciální systémové složky. Umístění těchto složek mohou mít různé hodnoty v různých operačních systémech, uživatel může změnit některé z míst a místa jsou lokalizována. Příklad speciální složky je systémová složka, která je "C:\WINDOWS\system32" na [!INCLUDE[winxp](../code-quality/includes/winxp_md.md)] ale "C:\WINNT\system32" na [!INCLUDE[win2kfamily](../code-quality/includes/win2kfamily_md.md)]. <xref:System.Environment.GetFolderPath%2A?displayProperty=fullName> Metoda vrátí umístění, které jsou přidružené k <xref:System.Environment.SpecialFolder> výčtu. Umístění, které jsou vráceny pomocí <xref:System.Environment.GetFolderPath%2A> jsou lokalizované a vhodné pro aktuálně spuštěný počítač.

 Toto pravidlo tokenizes, které se načítají pomocí cesty ke složkám <xref:System.Environment.GetFolderPath%2A> metoda do úrovní samostatný adresář. Každý řetězcového literálu je ve srovnání s tokeny. Pokud se najde shoda, se předpokládá, že metoda je vytváření řetězec, který označuje umístění systému, který je přidružený k tokenu. Přenositelnost a lokalizovatelnosti <xref:System.Environment.GetFolderPath%2A> metody k získání umístění speciální systémové složky namísto použití řetězcových literálů.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, načtěte umístění pomocí <xref:System.Environment.GetFolderPath%2A> metody.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Je bezpečné potlačit upozornění tohoto pravidla, pokud řetězcového literálu se nepoužívá k odkazování na jedno z umístění systému, které je přidružené <xref:System.Environment.SpecialFolder> výčtu.

## <a name="example"></a>Příklad
 Následující příklad vytvoří cesta běžné složka dat aplikace, které toto pravidlo generuje upozornění na tři. V dalším kroku příklad načte pomocí cesty <xref:System.Environment.GetFolderPath%2A> metody.

 [!code-csharp[FxCop.Globalization.HardcodedLocaleStrings#1](../code-quality/codesnippet/CSharp/ca1302-do-not-hardcode-locale-specific-strings_1.cs)]
 [!code-vb[FxCop.Globalization.HardcodedLocaleStrings#1](../code-quality/codesnippet/VisualBasic/ca1302-do-not-hardcode-locale-specific-strings_1.vb)]

## <a name="related-rules"></a>Související pravidla
 [CA1303: Nepředávejte literály jako lokalizované parametry](../code-quality/ca1303-do-not-pass-literals-as-localized-parameters.md)