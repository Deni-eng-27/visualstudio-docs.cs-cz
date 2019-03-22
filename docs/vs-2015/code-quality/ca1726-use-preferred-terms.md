---
title: 'CA1726: Použijte upřednostňované výrazy | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- UsePreferredTerms
- CA1726
helpviewer_keywords:
- UsePreferredTerms
ms.assetid: 642b2acd-3a33-4d1f-b0a7-67073ae73be2
caps.latest.revision: 24
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: e31c459d2d5ce8dc114605716c09f8360eca23d3
ms.sourcegitcommit: 3201da3499051768ab59f492699a9049cbc5c3c6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/22/2019
ms.locfileid: "58355209"
---
# <a name="ca1726-use-preferred-terms"></a>CA1726: Použijte upřednostňované výrazy
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější dokumentaci k sadě Visual Studio, naleznete v tématu [CA1726: Použijte upřednostňované výrazy](https://docs.microsoft.com/visualstudio/code-quality/ca1726-use-preferred-terms) na webu docs.microsoft.com.  
  
|||  
|-|-|  
|TypeName|UsePreferredTerms|  
|CheckId|CA1726|  
|Kategorie|Microsoft.Naming|  
|Narušující změna|Zásadní - při vyvolání na sestavení<br /><br /> Bez konce – při vyvolání na parametry typu|  
  
## <a name="cause"></a>příčina  
 Název externě viditelného identifikátoru zahrnuje výraz, pro který existuje alternativní upřednostňovaný výraz. Název případně obsahuje také výraz příznak nebo příznaky.  
  
## <a name="rule-description"></a>Popis pravidla  
 Toto pravidlo analyzuje identifikátor do tokenů. Každý jeden token a každou souvislých kombinaci duální tokenu je ve srovnání s podmínkami, které jsou integrované do pravidla a v části zastaralé vlastní slovníky. V následující tabulce jsou uvedeny podmínky, které jsou součástí pravidla a jejich preferované alternativy.  
  
|Zastaralé termín|Upřednostňovaný termín|  
|-------------------|--------------------|  
|nejsou|AreNot|  
|Zrušeno|Zrušeno|  
|Nemůžu|Cannot|  
|ComPlus|EnterpriseServices|  
|Nepovedlo|CouldNot|  
|Didnt|DidNot|  
|Doesnt|DoesNot|  
|Dont|DoNot|  
|Příznak nebo příznaky|Neexistuje žádné nahrazující výraz. Nepoužívejte.|  
|Hadnt|HadNot|  
|Nebyl|HasNot|  
|nebyly|HaveNot|  
|Indexy|Indexy|  
|není|IsNot|  
|Přihlášení|Přihlášení|  
|Odhlášení|LogOff|  
|Shouldnt|ShouldNot|  
|Přihlášení|SignIn|  
|Schvalování|Odhlášení|  
|Wasnt|WasNot|  
|nebyly|WereNot|  
|Wont|WillNot|  
|Wouldnt|WouldNot|  
|Zapisovatelný|Zápis|  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení tohoto pravidla, nahraďte výraz s alternativní upřednostňovaný výraz.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Potlačit upozornění tohoto pravidla pouze v případě, že je název identifikátoru je úmyslné a se vztahuje konkrétně k původní termín místo Upřednostňovaný termín.  
  
## <a name="related-rules"></a>Související pravidla  
 [Upozornění na pojmenování](../code-quality/naming-warnings.md)
