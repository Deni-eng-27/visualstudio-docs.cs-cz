---
title: 'CA1304: Zadejte možnosti CultureInfo | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- SpecifyCultureInfo
- CA1304
helpviewer_keywords:
- SpecifyCultureInfo
- CA1304
ms.assetid: b912d76a-54fd-4c93-b25d-16491e0ae319
caps.latest.revision: 22
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 3454dafe1766f67c1dcf89d738452f5eae4ef169
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42666417"
---
# <a name="ca1304-specify-cultureinfo"></a>CA1304: Zadejte možnosti CultureInfo
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CA1304: Zadejte CultureInfo](https://docs.microsoft.com/visualstudio/code-quality/ca1304-specify-cultureinfo).  
  
TypeName | SpecifyCultureInfo |  
| ID kontroly | CA1304 |  
| Kategorie | Microsoft.Globalization|  
| Zásadní změna | Ukončování bez |  
  
## <a name="cause"></a>příčina  
 Metoda nebo konstruktor volá člen, který má přetížení přijímající <xref:System.Globalization.CultureInfo?displayProperty=fullName> parametr a tato metoda nebo konstruktor nevolá přetížení přebírající <xref:System.Globalization.CultureInfo> parametru. Toto pravidlo ignoruje volání těchto metod:  
  
-   <xref:System.Activator.CreateInstance%2A?displayProperty=fullName>  
  
-   <xref:System.Resources.ResourceManager.GetObject%2A?displayProperty=fullName>  
  
-   <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=fullName>  
  
## <a name="rule-description"></a>Popis pravidla  
 Když <xref:System.Globalization.CultureInfo> nebo <xref:System.IFormatProvider?displayProperty=fullName> objektu není zadán, výchozí hodnota zadaná pomocí přetíženého členu nemusí mít ve všech národních prostředích požadovaný efekt. Navíc [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] členy zvolte výchozí jazykovou verzi a formátování podle předpokladů, které nemusí být správná pro váš kód. K zajištění, že kód funguje podle očekávání pro vaše scénáře, by měla poskytnout informace specifické jazykové verze podle následujících pokynů:  
  
-   Pokud uživateli se zobrazí hodnotu, použijte aktuální jazykové verze. Zobrazit <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName>.  
  
-   Pokud hodnota bude uložen a přístupný softwarem, to znamená, trvale uložena do souboru nebo databáze, pomocí neutrální jazykové verze. Zobrazit <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName>.  
  
-   Pokud si nejste jisti cílové hodnoty, mají příjemce dat nebo zprostředkovatele zadejte jazykovou verzi.  
  
 Všimněte si, že <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> slouží pouze k načítání lokalizovaných prostředků pomocí instance <xref:System.Resources.ResourceManager?displayProperty=fullName> třídy.  
  
 I v případě, že výchozí chování přetíženého členu je vhodné pro vaše potřeby, je lepší explicitně volat přetížení specifické pro jazykovou verzi tak, aby váš kód je držitelem dokumentů a snadněji zachována.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení tohoto pravidla, použijte přetížení přijímající <xref:System.Globalization.CultureInfo> nebo <xref:System.IFormatProvider> a zadat argument podle pokynů, které byly uvedeny dříve.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Je bezpečné potlačit upozornění tohoto pravidla, když je jisté, že je poskytovatel výchozí jazykové verze nebo formát správnou volbu a udržovatelnosti kódu není prioritou důležité vývojové.  
  
## <a name="example"></a>Příklad  
 V následujícím příkladu `BadMethod` způsobí, že dvě porušení tohoto pravidla. `GoodMethod` opravuje první porušení předáním System.String.Compare invariantní jazykovou verzi a předáním aktuální jazyková verze opravuje druhý porušení <xref:System.String.ToLower%2A> protože `string3` se zobrazí uživateli.  
  
 [!code-csharp[FxCop.Globalization.CultureInfo#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Globalization.CultureInfo/cs/FxCop.Globalization.CultureInfo.cs#1)]  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje účinek aktuální jazykovou verzi na výchozí <xref:System.IFormatProvider> , která se zvolila <xref:System.DateTime> typu.  
  
 [!code-csharp[FxCop.Globalization.IFormatProvider#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Globalization.IFormatProvider/cs/FxCop.Globalization.IFormatProvider.cs#1)]  
  
 Tento příklad vytvoří následující výstup.  
  
 **6/4/1900 12:15:12 HODIN**  
**06/04/1900 12:15:12**   
## <a name="related-rules"></a>Související pravidla  
 [CA1305: Zadejte možnosti IFormatProvider](../code-quality/ca1305-specify-iformatprovider.md)  
  
## <a name="see-also"></a>Viz také  
 [NIB: Pomocí třída CultureInfo](http://msdn.microsoft.com/en-us/d4329e34-64c3-4d1e-8c73-5b0ee626ba7a)



