---
title: 'CA2219: Nevyvolávejte výjimky v klauzulích výjimky'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- DoNotRaiseExceptionsInExceptionClauses
- CA2219
helpviewer_keywords:
- DoNotRaiseExceptionsInExceptionClauses
- CA2219
ms.assetid: 7b9b0bee-4e8e-49a4-8c40-52142b49061f
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 6a644cf3dc934676a14f1c5c59a6582fcd45ae7d
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62806651"
---
# <a name="ca2219-do-not-raise-exceptions-in-exception-clauses"></a>CA2219: Nevyvolávejte výjimky v klauzulích výjimky

|||
|-|-|
|TypeName|DoNotRaiseExceptionsInExceptionClauses|
|CheckId|CA2219|
|Kategorie|Microsoft.Usage|
|Narušující změna|Pevné dopadem na dřívější kód|

## <a name="cause"></a>Příčina
 Z je vyvolána výjimka `finally`, filtr nebo klauzule fault.

## <a name="rule-description"></a>Popis pravidla
 Když v klauzuli výjimka je vyvolána výjimka, výrazně zvyšuje obtížnost ladění.

 Když je výjimka vyvolána v `finally` nebo klauzule fault, nová výjimka skryje aktivní výjimku, pokud jsou k dispozici. To díky obtížné rozpoznání a ladění původní chyby.

 Pokud je v klauzuli filtru vyvolána výjimka, modul runtime bezobslužně zachytí výjimku a způsobí, že byl filtr vyhodnocen na hodnotu false. Neexistuje žádný způsob, jak zjistit rozdíl mezi vyhodnocení filtru na hodnotu false a výjimky se vyvolat z filtru. Tím je obtížné rozpoznat a ladit chyby v logice filtru.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li vyřešit porušení tohoto pravidla, nevyvolávejte explicitně výjimky z `finally`, filtr nebo klauzule fault.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění tohoto pravidla. Nejsou žádné scénáře, kdy výjimka vyvolána v klauzuli výjimek poskytuje výhoda pro provádění kódu.

## <a name="related-rules"></a>Související pravidla
 [CA1065: Nevyvolávejte výjimky v neočekávaných umístěních](../code-quality/ca1065-do-not-raise-exceptions-in-unexpected-locations.md)

## <a name="see-also"></a>Viz také:
 [Upozornění ohledně návrhu](../code-quality/design-warnings.md)