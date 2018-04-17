---
title: 'CA1302: Proveďte závislé konkrétní řetězce národního prostředí | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
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
ms.workload:
- multiple
ms.openlocfilehash: f01bcbf0d717ff8728d87b55f2cfd1c7c5af34d3
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="ca1302-do-not-hardcode-locale-specific-strings"></a>CA1302: Nekódujte pevně řetězce závislé na národním prostředí
|||  
|-|-|  
|TypeName|DoNotHardcodeLocaleSpecificStrings|  
|CheckId|CA1302|  
|Kategorie|Microsoft.Globalization|  
|Narušující změna|Nenarušující|  
  
## <a name="cause"></a>příčina  
 Metoda používá literálu řetězec, který představuje část cesty určitých systémových složek.  
  
## <a name="rule-description"></a>Popis pravidla  
 <xref:System.Environment.SpecialFolder?displayProperty=fullName> Výčet obsahuje členy, které odkazují na speciální systémových složek. Umístění těchto složek může mít různé hodnoty v různých operačních systémech, uživatel může změnit některé z umístění a lokalizace umístění. Příkladem speciální složky je systémová složka, která je "C:\WINDOWS\system32" na [!INCLUDE[winxp](../code-quality/includes/winxp_md.md)] ale "C:\WINNT\system32" na [!INCLUDE[win2kfamily](../code-quality/includes/win2kfamily_md.md)]. <xref:System.Environment.GetFolderPath%2A?displayProperty=fullName> Metoda vrátí umístění, které jsou přidružené <xref:System.Environment.SpecialFolder> výčtu. Umístění, která se vrátí pomocí <xref:System.Environment.GetFolderPath%2A> lokalizace a vhodné pro aktuálně spuštěné počítač.  
  
 Toto pravidlo tokenizes cesty složky, které se načítají pomocí <xref:System.Environment.GetFolderPath%2A> metoda do samostatné directory úrovní. Tokeny se porovná s každou řetězcový literál. Pokud je nalezena shoda, předpokládá se, že je metoda vytváření řetězec, který odkazuje na umístění systému, který je přidružen token. Přenositelnost a lokalizovatelnost najdete <xref:System.Environment.GetFolderPath%2A> metoda pro načtení umístění speciální systémových složek, místo použití textové literály.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení toto pravidlo, načíst umístění pomocí <xref:System.Environment.GetFolderPath%2A> metoda.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Je bezpečné potlačit upozornění na toto pravidlo, pokud řetězcový literál se nepoužívá k odkazování na jednu z umístění systému, které je přidružené <xref:System.Environment.SpecialFolder> výčtu.  
  
## <a name="example"></a>Příklad  
 Následující příklad vytvoří cestu běžné složce data aplikací, což je toto pravidlo generuje upozornění na tři. V příkladu dále načte cestu pomocí <xref:System.Environment.GetFolderPath%2A> metoda.  
  
 [!code-csharp[FxCop.Globalization.HardcodedLocaleStrings#1](../code-quality/codesnippet/CSharp/ca1302-do-not-hardcode-locale-specific-strings_1.cs)]
 [!code-vb[FxCop.Globalization.HardcodedLocaleStrings#1](../code-quality/codesnippet/VisualBasic/ca1302-do-not-hardcode-locale-specific-strings_1.vb)]  
  
## <a name="related-rules"></a>Související pravidla  
 [CA1303: Nepředávejte literály jako lokalizované parametry](../code-quality/ca1303-do-not-pass-literals-as-localized-parameters.md)