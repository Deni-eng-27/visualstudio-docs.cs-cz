---
title: 'CA1703: Řetězce prostředků by měly být zadány správně | Microsoft Docs'
ms.date: 03/28/2018
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- ResourceStringsShouldBeSpelledCorrectly
- CA1703
helpviewer_keywords:
- CA1703
- ResourceStringsShouldBeSpelledCorrectly
ms.assetid: 693f4970-f512-40cb-ae3b-a0f3a5c6d6f1
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: dbd0fdccc9ee57223a6684b9caac191f1705c91c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="ca1703-resource-strings-should-be-spelled-correctly"></a>CA1703: Řetězce prostředků by měly být zadány správně

|||
|-|-|
|TypeName|ResourceStringsShouldBeSpelledCorrectly|
|CheckId|CA1703|
|Kategorie|Microsoft.Naming|
|Narušující změna|Nenarušující|

## <a name="cause"></a>příčina

Zdrojový řetězec obsahuje jedno nebo více slov, která knihovna kontroly pravopisu společnosti Microsoft nerozpoznala.

## <a name="rule-description"></a>Popis pravidla

Toto pravidlo analyzuje řetězec prostředku do slova (tokenizaci složených slov) a kontroluje, zda každý word/token. Informace o analýzy algoritmus najdete v tématu [CA1704: identifikátory by měly být zadány správně](../code-quality/ca1704-identifiers-should-be-spelled-correctly.md).

## <a name="how-to-fix-violations"></a>Jak opravit porušení

Chcete-li opravit porušení toto pravidlo, použijte dokončení slova, která jsou správně napsán, nebo přidejte slova do slovníku. Informace o tom, jak používat vlastní slovník najdete v tématu [CA1704: identifikátory by měly být zadány správně](../code-quality/ca1704-identifiers-should-be-spelled-correctly.md).

## <a name="change-the-dictionary-language"></a>Změnit jazyk slovníku

Ve výchozím nastavení se používá verze Angličtina (en) nástroj pro kontrolu pravopisu. Pokud chcete změnit jazyk pravopisu, můžete to udělat tak přidáním jednu z těchto atributů k vaší *AssemblyInfo.cs* nebo *AssemblyInfo.vb* souboru:

- Použití <xref:System.Reflection.AssemblyCultureAttribute> zadat jazykovou verzi, pokud jsou vaše prostředky v satelitní sestavení.
- Použití <xref:System.Resources.NeutralResourcesLanguageAttribute> k určení *neutrální jazykovou verzi* vašeho sestavení, pokud vaše prostředky jsou ve stejném sestavení jako váš kód.

> [!IMPORTANT]
> Pokud nastavíte jazykovou verzi na jakoukoli jinou hodnotu než jazykovou verzi na základě angličtina, je tato pravidel nástroje Analýza kódu bezobslužně zakázané.

## <a name="when-to-suppress-warnings"></a>Při potlačení upozornění

Nepotlačujte upozornění na toto pravidlo. Správně hláskovaným slova zkrátit čas, který je potřeba další nové knihovny softwaru.

## <a name="related-rules"></a>Související pravidla

- [CA1701: Malá a velká písmena složených slov prostředku řetězců by měla být použita správně](../code-quality/ca1701-resource-string-compound-words-should-be-cased-correctly.md)
- [CA1704: Identifikátory by měly být zadány správně](../code-quality/ca1704-identifiers-should-be-spelled-correctly.md)
- [CA2204: Literály by měly být zadány správně](../code-quality/ca2204-literals-should-be-spelled-correctly.md)