---
title: 'CA1704: Identifikátory by měly být zadány správně'
ms.date: 03/28/2018
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- CA1704
- IdentifiersShouldBeSpelledCorrectly
helpviewer_keywords:
- CA1704
- IdentifiersShouldBeSpelledCorrectly
ms.assetid: f2c7a44d-1690-44ca-9cd0-681b04b12b2a
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: cfb91c830239a61b3f7f7e58364ae41c87152321
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54935654"
---
# <a name="ca1704-identifiers-should-be-spelled-correctly"></a>CA1704: Identifikátory by měly být zadány správně

|||
|-|-|
|TypeName|IdentifiersShouldBeSpelledCorrectly|
|CheckId|CA1704|
|Kategorie|Microsoft.Naming|
|Narušující změna|Narušující|

## <a name="cause"></a>Příčina

Název identifikátoru obsahuje jedno nebo více slov, která knihovna kontroly pravopisu společnosti Microsoft nerozpoznala. Toto pravidlo není zkontrolujte konstruktory nebo členy s názvem speciální, jako je například get a nastavte přistupující objekty vlastnosti.

## <a name="rule-description"></a>Popis pravidla

Toto pravidlo analyzuje identifikátor do tokenů a zkontroluje pravopis pro každý token. Parsování algoritmus provede následující transformace:

- Velká písmena spustit nový token. Například MyNameIsJoe tokenizes "My", "Name", "Je", "Jan".

- Více velkých písmen spustí poslední velké písmeno nový token. Například GUIEditor tokenizes na "Grafického uživatelského rozhraní", "Editoru".

- Úvodní a koncové apostrofy se odeberou. Například 'sender' tokenizes na "sender".

- Podtržítka místo koncový token a se odeberou. Například Hello_world tokenizes na "Hello"; "world".

- Odeberou se tyto vložené znaky. Například pro & mat tokenizes na "format".

## <a name="language"></a>Jazyk

Nástroj pro kontrolu pravopisu aktuálně zkontroluje pouze proti jazykovou verzi na základě angličtina slovníky. Jazyková verze projektu v souboru projektu, můžete změnit tak, že přidáte **CodeAnalysisCulture** elementu.

Příklad:

```xml
<Project ...>
  <PropertyGroup>
    <CodeAnalysisCulture>en-AU</CodeAnalysisCulture>
```

> [!IMPORTANT]
> Pokud nastavíte jazykovou verzi na jinou hodnotu než jazykovou verzi na základě angličtina, tento pravidel nástroje Analýza kódu je tiše zakázaná.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

Chcete-li opravit porušení tohoto pravidla, opravte pravopis slova nebo přidejte slovo do vlastního slovníku.

### <a name="to-add-words-to-a-custom-dictionary"></a>Chcete-li přidat slova do vlastního slovníku

Název souboru vlastního slovníku XML *CustomDictionary.xml*. Umístit do slovníku v instalačním adresáři nástroje adresáři projektu nebo do adresáře, který je přidružený k nástroji v rámci profilu uživatele (*%USERPROFILE%\Application Data\\...* ). Zjistěte, jak přidat vlastní slovník do projektu v sadě Visual Studio, najdete v článku [jak: Přizpůsobení slovníku analýzy kódu](../code-quality/how-to-customize-the-code-analysis-dictionary.md).

- Přidáte slova, která by nemělo způsobit narušení v rámci slovníku/slova/Recognized cesty.

- Přidáte slova, která by neměly způsobit narušení v cestě slovníku/slova/Nerozpoznán.

- Přidáte slova, která by měla být označena jako zastaralá v cestě slovníku/slova nebo zastaralé funkce. Naleznete v tématu související pravidlo [CA1726: Použijte upřednostňované výrazy](../code-quality/ca1726-use-preferred-terms.md) Další informace.

- Přidáte výjimky pravidla malých a velkých písmen zkratka do slovníku nebo zkratky/CasingExceptions cesty.

Následuje příklad struktury souboru vlastního slovníku:

```xml
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

- [CA2204: Literály by měly být zadány správně](../code-quality/ca2204-literals-should-be-spelled-correctly.md)
- [CA1703: Řetězce prostředků by měly být zadány správně](../code-quality/ca1703-resource-strings-should-be-spelled-correctly.md)
- [CA1709: Identifikátory by měly správně formátováno.](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)
- [CA1708: Identifikátory by se měly lišit o více než velikostí písmen](../code-quality/ca1708-identifiers-should-differ-by-more-than-case.md)
- [CA1707: Identifikátory by neměly obsahovat podtržítka](../code-quality/ca1707-identifiers-should-not-contain-underscores.md)
- [CA1726: Použijte upřednostňované výrazy](../code-quality/ca1726-use-preferred-terms.md)

## <a name="see-also"></a>Viz také:

- [Postupy: Přizpůsobení slovníku analýzy kódu](../code-quality/how-to-customize-the-code-analysis-dictionary.md)
