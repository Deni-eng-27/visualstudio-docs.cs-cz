---
title: 'CA1704: Identifikátory by měly být zadány správně | Dokumentace Microsoftu'
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
- CA1704
- IdentifiersShouldBeSpelledCorrectly
helpviewer_keywords:
- CA1704
- IdentifiersShouldBeSpelledCorrectly
ms.assetid: f2c7a44d-1690-44ca-9cd0-681b04b12b2a
caps.latest.revision: 27
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: f8b46075a1ca9058f111f33b9b1354613a54e88d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42680838"
---
# <a name="ca1704-identifiers-should-be-spelled-correctly"></a>CA1704: Identifikátory by měly být zadány správně
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CA1704: identifikátory by měly být zadány správně](https://docs.microsoft.com/visualstudio/code-quality/ca1704-identifiers-should-be-spelled-correctly).  
  
TypeName | IdentifiersShouldBeSpelledCorrectly |  
| ID kontroly | CA1704 |  
| Kategorie | Microsoft.Naming|  
| Zásadní změna | Zásadní |  
  
## <a name="cause"></a>příčina  
 Název identifikátoru obsahuje jedno nebo více slov, která knihovna kontroly pravopisu společnosti Microsoft nerozpoznala. Toto pravidlo není zkontrolujte konstruktory nebo členy s názvem speciální, jako je například get a nastavte přistupující objekty vlastnosti.  
  
## <a name="rule-description"></a>Popis pravidla  
 Toto pravidlo analyzuje identifikátor do tokenů a zkontroluje pravopis pro každý token. Parsování algoritmus provede následující transformace:  
  
-   Velká písmena spustit nový token. Například MyNameIsJoe tokenizes "My", "Name", "Je", "Jan".  
  
-   Více velkých písmen spustí poslední velké písmeno nový token. Například GUIEditor tokenizes na "Grafického uživatelského rozhraní", "Editoru".  
  
-   Úvodní a koncové apostrofy se odeberou. Například 'sender' tokenizes na "sender".  
  
-   Podtržítka místo koncový token a se odeberou. Například Hello_world tokenizes na "Hello"; "world".  
  
-   Odeberou se tyto vložené znaky. Například pro & mat tokenizes na "format".  
  
 Ve výchozím nastavení je použít nástroj pro kontrolu pravopisu verze Angličtina (en). Jsou nyní dostupné bez dalších slovníků jazyků.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení tohoto pravidla, opravte pravopis slova nebo přidejte slovo do vlastního slovníku, který je pojmenován CustomDictionary.xml. Umístit do slovníku v instalačním adresáři nástroje adresáři projektu nebo do adresáře, který je přidružený k nástroji v rámci profilu uživatele (%USERPROFILE%\Application Data\\...). Další informace o přidání do projektu ve slovníku [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], naleznete v tématu [postupy: přizpůsobení slovníku analýzy kódu](../code-quality/how-to-customize-the-code-analysis-dictionary.md)  
  
-   Přidáte slova, která by nemělo způsobit narušení v rámci slovníku/slova/Recognized cesty.  
  
-   Přidáte slova, která by neměly způsobit narušení v cestě slovníku/slova/Nerozpoznán.  
  
-   Přidáte slova, která by měla být označena jako zastaralá v cestě slovníku/slova nebo zastaralé funkce. Naleznete v tématu související pravidlo [CA1726: použijte upřednostňované výrazy](../code-quality/ca1726-use-preferred-terms.md)Další informace.  
  
-   Přidáte výjimky pravidla malých a velkých písmen zkratka do slovníku nebo zkratky/CasingExceptions cesty.  
  
 Následuje příklad struktury souboru vlastního slovníku.  
  
```  
<Dictionary>  
   <Words>  
      <Unrecognized>  
         <Word>cb</Word>  
      </Unrecognized>  
      <Recognized>  
         <Word>stylesheet</Word>  
         <Word>GotDotNet</Word>  
      </Recognized>  
      <Deprecated>  
         <Term PreferredAlternate="EnterpriseServices">ComPlus</Term>  
      </Deprecated>  
   </Words>  
   <Acronyms>  
      <CasingExceptions>  
         <Acronym>CJK</Acronym>  
         <Acronym>Pi</Acronym>  
      </CasingExceptions>  
   </Acronyms>  
</Dictionary>  
```  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Potlačit upozornění tohoto pravidla pouze v případě, že je záměrně chybně napsaná slova a slovo platí pro omezenou sadu knihovny. Správně hláskovaným slov snížit učit se, která je požadována pro nové knihovny softwaru.  
  
## <a name="related-rules"></a>Související pravidla  
 [CA2204: Literály by měly být zadány správně](../code-quality/ca2204-literals-should-be-spelled-correctly.md)  
  
 [CA1703: Řetězce prostředků by měly být zadány správně](../code-quality/ca1703-resource-strings-should-be-spelled-correctly.md)  
  
 [CA1709: Malá a velká písmena identifikátorů by měla být použita správně](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)  
  
 [CA1708: Identifikátory by se měly lišit více než použitím malých a velkých písmen](../code-quality/ca1708-identifiers-should-differ-by-more-than-case.md)  
  
 [CA1707: Identifikátory by neměly obsahovat podtržítka](../code-quality/ca1707-identifiers-should-not-contain-underscores.md)  
  
 [CA1726: Použijte upřednostňované výrazy](../code-quality/ca1726-use-preferred-terms.md)  
  
## <a name="see-also"></a>Viz také  
 [Postupy: Přizpůsobení slovníku Analýzy kódu](../code-quality/how-to-customize-the-code-analysis-dictionary.md)



