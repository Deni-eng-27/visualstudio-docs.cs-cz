---
title: 'CA1505: Vyhněte se neudržovatelnému kódu | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- AvoidUnmaintainableCode
- CA1505
helpviewer_keywords:
- AvoidUnmaintainableCode
- CA1505
ms.assetid: 8292b268-5929-4221-b699-f9c414bcec5d
caps.latest.revision: 16
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 87aacfd675181e35d289b2a054c58f83f3f790fa
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/19/2019
ms.locfileid: "72607591"
---
# <a name="ca1505-avoid-unmaintainable-code"></a>CA1505: Vyhněte se neudržovatelnému kódu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|AvoidUnmantainableCode|
|CheckId|CA1505|
|Kategorie|Microsoft. udržovatelnost|
|Narušující změna|Nenarušující|

## <a name="cause"></a>příčina
 Typ nebo metoda má nízkou hodnotu indexu udržovatelnosti.

## <a name="rule-description"></a>Popis pravidla
 Index udržovatelnosti se počítá pomocí následujících metrik: řádků kódu, programu Volume a cyklomatická složitosti. Objem programu je míra obtížnosti porozumění typu nebo metodě, která je založena na počtu operátorů a operandů v kódu. Složitosti cyklomatická je míra strukturální složitosti typu nebo metody. Můžete získat další informace o metrikách kódu při [Měření složitosti a udržovatelnosti spravovaného kódu](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md).

 Nízký index udržovatelnosti indikuje, že typ nebo metoda je pravděpodobně obtížné udržovat a že by bylo dobrým kandidátem na přepracování.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li toto porušení opravit, změňte návrh typu nebo metodu a pokuste se ji rozdělit na menší a více zaměřené typy nebo metody.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Vylučte toto upozornění, pokud je typ nebo metoda stále považována za udržovatelnou bez ohledu na její velkou velikost nebo když typ nebo metodu nelze rozdělit.

## <a name="see-also"></a>Viz také
 [Upozornění na udržovatelnost](../code-quality/maintainability-warnings.md) při [Měření složitosti a udržovatelnosti spravovaného kódu](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md)
