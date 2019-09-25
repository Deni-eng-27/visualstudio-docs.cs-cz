---
title: 'CA1704: Identifikátory by měly být zadány správně'
ms.date: 03/28/2018
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
ms.openlocfilehash: fa04ca237134c1947b5c58b921f87f32a1ecfb16
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/24/2019
ms.locfileid: "71234295"
---
# <a name="ca1704-identifiers-should-be-spelled-correctly"></a>CA1704: Identifikátory by měly být zadány správně

|||
|-|-|
|TypeName|IdentifiersShouldBeSpelledCorrectly|
|CheckId|CA1704|
|Kategorie|Microsoft.Naming|
|Zásadní změna|Narušující|

## <a name="cause"></a>příčina

Název identifikátoru obsahuje jedno nebo více slov, která knihovna kontroly pravopisu společnosti Microsoft nerozpoznala. Toto pravidlo nekontroluje konstruktory nebo členy se speciálním jménem, jako jsou například GET a Set Access Property.

## <a name="rule-description"></a>Popis pravidla

Toto pravidlo analyzuje identifikátor na tokeny a kontroluje pravopis každého tokenu. Algoritmus analýzy provádí následující transformace:

- Velká písmena zahájí nový token. Například MyNameIsJoe tokenizes na "my", "Name", "is", "Jana".

- U více velkých písmen začíná poslední velké písmeno novému tokenu. Například GUIEditor tokenizes na "GUI", "Editor".

- Úvodní a koncové apostrofy jsou odebrány. Například "Sender" tokenizes na "Sender".

- Podtržítka označují konec tokenu a jsou odebrána. Například hello_world tokenizes na "Hello", "World".

- Vložené ampersandy se odeberou. Například pro & mat tokenizes do formátu "Format".

## <a name="language"></a>Jazyk

Kontrola pravopisu aktuálně kontroluje pouze proti slovníkům jazykové verze v angličtině. Můžete změnit jazykovou verzi projektu v souboru projektu přidáním elementu **CodeAnalysisCulture** .

Příklad:

```xml
<Project ...>
  <PropertyGroup>
    <CodeAnalysisCulture>en-AU</CodeAnalysisCulture>
```

> [!IMPORTANT]
> Pokud nastavíte jazykovou verzi na jinou než anglickou jazykovou verzi, toto pravidlo analýzy kódu je tiše zakázané.

## <a name="how-to-fix-violations"></a>Jak opravit porušení

Chcete-li opravit porušení tohoto pravidla, opravte pravopis slova nebo přidejte slovo do vlastního slovníku.

### <a name="to-add-words-to-a-custom-dictionary"></a>Přidání slov do vlastního slovníku

Pojmenujte soubor XML vlastního slovníku *CustomDictionary. XML*. Umístěte slovník do instalačního adresáře nástroje, adresáře projektu nebo v adresáři, který je přidružen k nástroji v rámci profilu uživatele ( *%UserProfile%\Application data\\...* ). Další informace o tom, jak přidat vlastní slovník do projektu v aplikaci Visual Studio, [naleznete v tématu How to: Přizpůsobení slovníku](../code-quality/how-to-customize-the-code-analysis-dictionary.md)analýzy kódu.

- Přidejte slova, která by neměla způsobovat porušení v rámci slovníku/slov/rozpoznané cesty.

- Přidejte slova, která by měla způsobit porušení v rámci slovníku/slov/nerozpoznaná cesta.

- Přidejte slova, která by měla být označena příznakem jako zastaralá v cestě Dictionary/Word/zastaralá cesta. Podívejte se na téma [související pravidlo CA1726: Pro další informace](../code-quality/ca1726-use-preferred-terms.md) použijte preferované výrazy.

- Do slovníku/akronymy/CasingExceptions cesty přidejte výjimky do pravidel pro velká a malá písmena.

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

Potlačí upozornění z tohoto pravidla pouze v případě, že je slovo úmyslně špatně napsané a slovo se vztahuje na omezené sady knihovny. Správná pravopisná slova omezují výukovou křivku, která je požadována pro nové knihovny softwaru.

## <a name="related-rules"></a>Související pravidla

- [CA2204: Literály by měly být zadány správně](../code-quality/ca2204-literals-should-be-spelled-correctly.md)
- [CA1703: Řetězce prostředků by měly být zadány správně](../code-quality/ca1703-resource-strings-should-be-spelled-correctly.md)
- [CA1709: Identifikátory by se měly použita správně.](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)
- [CA1708: Identifikátory by se měly lišit o více než malých písmenech](../code-quality/ca1708-identifiers-should-differ-by-more-than-case.md)
- [CA1707: Identifikátory by neměly obsahovat podtržítka](../code-quality/ca1707-identifiers-should-not-contain-underscores.md)
- [CA1726: Použít preferované výrazy](../code-quality/ca1726-use-preferred-terms.md)

## <a name="see-also"></a>Viz také:

- [Postupy: Přizpůsobení slovníku analýzy kódu](../code-quality/how-to-customize-the-code-analysis-dictionary.md)
