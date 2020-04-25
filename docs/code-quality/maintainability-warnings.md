---
title: Upozornění udržovatelnosti
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.codeanalysis.maintainabilityrules
helpviewer_keywords:
- warnings, maintainability
- managed code analysis warnings, maintainability warnings
- maintainability warnings
ms.assetid: 537e70ca-a88c-49df-bfc7-0ee63bbe4f16
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: fd7fe79665ac8de665116a6832d5ef9327fb356c
ms.sourcegitcommit: dab57cebd484228e6f0cf7ab1b9685c575410c06
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/25/2020
ms.locfileid: "82152982"
---
# <a name="maintainability-warnings"></a>Upozornění udržovatelnosti

Upozornění udržovatelnosti podporují údržbu knihovny a aplikace.

## <a name="in-this-section"></a>V tomto oddílu

| Pravidlo | Popis |
|-----------|-----------------------------------|
| [CA1500: Názvy proměnných by neměly odpovídat názvům polí](../code-quality/ca1500.md) | Metoda instance deklaruje parametr nebo místní proměnnou, jejíž název odpovídá poli instance deklarovaného typu, který vede k chybám. |
| [CA1501: Vyhněte se nadměrné dědičnosti](../code-quality/ca1501.md) | Typ je více než čtyři úrovně hluboko v hierarchii dědičnosti. Hluboce vnořené hierarchie typů může být obtížné sledovat, pochopit a udržovat. |
| [CA1502: Vyhněte se nadměrné složitosti](../code-quality/ca1502.md) | Toto pravidlo měří počet lineárně nezávislých cest skrze metodu, což je určeno počtem a složitostí podmínkových větví. |
| [CA1504: Revize zavádějících názvů polí](../code-quality/ca1504.md) | Název pole instance začíná řetězcem "s_", nebo název statického (sdíleného [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]) pole začíná řetězcem "m_". |
| [CA1505: Vyhněte se neudržovatelnému kódu](../code-quality/ca1505.md) | Typ nebo metoda má nízkou hodnotu indexu udržovatelnosti. Nízký index udržovatelnosti označuje, že typ nebo metodu je pravděpodobně obtížné udržovat a je vhodné ji znovu navrhnout. |
| [CA1506: Vyhněte se nadměrnému párování tříd](../code-quality/ca1506.md) | Toto pravidlo měří párování tříd podle počtu jedinečných odkazů na typ, které typ nebo metoda obsahuje. |
| [CA1507: místo řetězce použijte nameof.](../code-quality/ca1507.md) | Řetězcový literál se používá jako argument, ve kterém by `nameof` se mohl použít výraz. |
| [CA1508: Vyhněte se neaktivnímu podmíněnému kódu](../code-quality/ca1508.md) | Metoda má podmíněný kód, který se vždy vyhodnocuje `true` za `false` běhu nebo za běhu. To vede k nedoručenému kódu `false` ve větvi podmínky. |

## <a name="see-also"></a>Viz také

- [Měření složitosti a udržovatelnosti spravovaného kódu](../code-quality/code-metrics-values.md)
