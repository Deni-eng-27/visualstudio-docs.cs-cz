---
title: 'CA1700: Nejmenujte vyhrazené hodnoty &#39;výčtu&#39;'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1700
- DoNotNameEnumValuesReserved
helpviewer_keywords:
- DoNotNameEnumValuesReserved
- CA1700
ms.assetid: 7a7e01c3-ae7d-4c82-a646-91b58864a749
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 7642885a953f4974a9440acced027552bd64f72e
ms.sourcegitcommit: 485ffaedb1ade71490f11cf05962add1718945cc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/16/2019
ms.locfileid: "72439990"
---
# <a name="ca1700-do-not-name-enum-values-39reserved39"></a>CA1700: Nejmenujte vyhrazené hodnoty &#39;výčtu&#39;

|||
|-|-|
|TypeName|DoNotNameEnumValuesReserved|
|CheckId|CA1700|
|Kategorie|Microsoft. pojmenování|
|Zásadní změna|Narušující|

## <a name="cause"></a>příčina

Název členu výčtu obsahuje slovo "rezervované".

## <a name="rule-description"></a>Popis pravidla

Toto pravidlo předpokládá, že člen výčtu, který má název obsahující výraz „reserved“, není aktuálně používán, ale je zástupným symbolem k přejmenování nebo odstranění v budoucí verzi. Přejmenování nebo odstranění členu je narušující změna. Neměli byste očekávat, že uživatelé budou ignorovat člena, protože jeho název obsahuje "rezervované", ani vám nemůžete spoléhat na to, že se v dokumentaci budou číst nebo přidržet. Vzhledem k tomu, že se rezervované členy zobrazují v prohlížečích objektů a inteligentních vývojových prostředích, mohou způsobit nejasnost o tom, které členy jsou skutečně používány.

Místo použití rezervovaného člena přidejte do výčtu v budoucí verzi nového člena. Ve většině případů není přidání nového člena zásadní změnou, pokud sčítání nezpůsobí změnu hodnot původních členů.

V omezeném počtu případů je přidání člena zásadní změnou, i když původní hodnoty zachovají původní členové. Primárně nelze vrátit nového člena z existujících cest kódu bez koncových volajících, které používají příkaz `switch` (`Select` v [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]) pro návratovou hodnotu, která zahrnuje celý seznam členů a který vyvolal výjimku ve výchozím případu. Sekundárním problémem je, že klientský kód nemusí zpracovávat změnu v chování z metod reflexe, jako je <xref:System.Enum.IsDefined%2A?displayProperty=fullName>. V případě, že by se měl nový člen vrátit z existujících metod nebo dojde k nekompatibilitě známé aplikace z důvodu nedostatečného využití reflexe, jediného nepřerušeného řešení je:

1. Přidejte nový výčet, který obsahuje původní a nové členy.

2. Označte původní výčet atributem <xref:System.ObsoleteAttribute?displayProperty=fullName>.

   Použijte stejný postup pro všechny externě viditelné typy nebo členy, které zveřejňují původní výčet.

## <a name="how-to-fix-violations"></a>Jak opravit porušení

Chcete-li opravit porušení tohoto pravidla, odeberte nebo přejmenujte člena.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Z tohoto pravidla je bezpečné potlačit upozornění pro člena, který se právě používá, nebo pro knihovny, které byly dřív dodány.

## <a name="related-rules"></a>Související pravidla

[CA2217: Neoznačujte výčty pomocí FlagsAttribute](../code-quality/ca2217.md)

[CA1712: Nezačínejte hodnoty výčtu s názvem typu](../code-quality/ca1712-do-not-prefix-enum-values-with-type-name.md)

[CA1028: Úložiště výčtu by měl být Int32](../code-quality/ca1028-enum-storage-should-be-int32.md)

[CA1008: Výčty by měly mít nulovou hodnotu](../code-quality/ca1008-enums-should-have-zero-value.md)

[CA1027: Označte výčty pomocí FlagsAttribute](../code-quality/ca1027-mark-enums-with-flagsattribute.md)
