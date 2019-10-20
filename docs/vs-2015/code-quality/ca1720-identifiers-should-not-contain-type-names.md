---
title: 'CA1720: identifikátory by neměly obsahovat názvy typů | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1720
- IdentifiersShouldNotContainTypeNames
helpviewer_keywords:
- IdentifiersShouldNotContainTypeNames
- CA1720
ms.assetid: c95ee48f-f23a-45f0-ac9e-a3c1ecfabdea
caps.latest.revision: 17
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 34ebe4848bbbe49b9a67449795f0aea7d104af8b
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/19/2019
ms.locfileid: "72671629"
---
# <a name="ca1720-identifiers-should-not-contain-type-names"></a>CA1720: Identifikátory by neměly obsahovat názvy typů
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|IdentifiersShouldNotContainTypeNames|
|CheckId|CA1720|
|Kategorie|Microsoft. pojmenování|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Název parametru v externě viditelném členu obsahuje název datového typu.

 -nebo-

 Název externě viditelného členu obsahuje název datového typu specifický pro jazyk.

## <a name="rule-description"></a>Popis pravidla
 Názvy parametrů a členů jsou lépe použity ke sdělení jejich významu, než aby bylo možné popsat jejich typ, který je třeba poskytnout pomocí vývojářských nástrojů. V případě názvů členů, pokud je třeba použít název datového typu, použijte název nezávislá na jazyce, nikoli na konkrétní jazyk. Například namísto názvu C# typu int použijte název datového typu nezávislý na jazyku, Int32.

 Všechny diskrétní tokeny v názvu parametru nebo členu jsou zkontrolovány proti následujícím jazykově specifickým názvům datových typů, a to při nerozlišování velkých a malých písmen:

- Logick

- WChar

- Int8

- UInt8

- Dostatečná

- UShort

- Hmot

- UInt

- Integer

- UInteger –

- Dlouhou

- ULong

- Celé

- Podpisy

- Plovák

- Float32

- Float64

  Kromě toho názvy parametrů jsou také zkontrolovány proti následujícím jazykově nezávislým názvům datových typů, a to při nerozlišování velkých a malých písmen:

- Objekt

- Objektu

- Boolean

- Char

- String

- SByte

- Byte

- UByte

- Int16

- UInt16

- Int32

- UInt32

- Int64

- UInt64

- IntPtr

- Střed

- Ukazatele

- UInptr

- UPtr

- UPointer

- Single

- Double

- Desetinné číslo

- Hlavních

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 **Je-li aktivováno proti parametru:**

 Nahraďte identifikátor datového typu v názvu parametru výrazem, který lépe popisuje svůj význam nebo obecnější výraz, jako je hodnota.

 **Při vyvolání proti členovi:**

 Nahraďte identifikátor datového typu specifický pro jazyk v názvu člena termínem, který lépe popisuje svůj význam, ekvivalent nezávislého jazyka nebo obecnější výraz, jako je hodnota.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Příležitostné použití parametrů založených na typu a názvů členů může být vhodné. Pro nový vývoj ale nedochází k žádným známým scénářům, kdy byste měli potlačit upozornění od tohoto pravidla. U knihoven, které mají předchozí dodané, možná budete muset potlačit upozornění od tohoto pravidla.

## <a name="related-rules"></a>Související pravidla
 [CA1709: Malá a velká písmena identifikátorů by měla být použita správně](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)

 [CA1708: Identifikátory by se měly lišit více než použitím malých a velkých písmen](../code-quality/ca1708-identifiers-should-differ-by-more-than-case.md)

 [CA1707: Identifikátory by neměly obsahovat podtržítka](../code-quality/ca1707-identifiers-should-not-contain-underscores.md)

 [CA1719: Názvy parametrů by neměly odpovídat názvům členů](../code-quality/ca1719-parameter-names-should-not-match-member-names.md)
