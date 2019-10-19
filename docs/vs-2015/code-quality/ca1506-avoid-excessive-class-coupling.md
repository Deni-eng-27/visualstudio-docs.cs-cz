---
title: 'CA1506: Vyhněte se nadměrnému párování tříd | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- AvoidExcessiveClassCoupling
- CA1506
helpviewer_keywords:
- AvoidExcessiveClassCoupling
- CA1506
ms.assetid: 9f0943c0-e802-4e3f-8798-2ab8653ddc80
caps.latest.revision: 14
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: e85ac61e404ac9bc1afb9459716c2395233c5080
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/19/2019
ms.locfileid: "72607410"
---
# <a name="ca1506-avoid-excessive-class-coupling"></a>CA1506: Vyhněte se nadměrnému párování tříd
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|AvoidExcessiveClassCoupling|
|CheckId|CA1506|
|Kategorie|Microsoft. udržovatelnost|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Typ nebo metoda jsou spojeny s mnoha dalšími typy.

## <a name="rule-description"></a>Popis pravidla
 Toto pravidlo měří párování tříd podle počtu jedinečných odkazů na typ, které typ nebo metoda obsahuje.

 Typy a metody s vysokým stupněm párování tříd může být obtížné udržovat. Je dobrým zvykem mít typy a metody, které mají slabý spoj a vysokou soudržnost.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li toto porušení opravit, zkuste změnit návrh typu nebo metody tak, aby se snížil počet typů, ke kterým je párování.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Toto upozornění vylučte, pokud je typ nebo metoda stále považována za udržovatelnou bez ohledu na jejich velký počet závislostí na jiných typech.

## <a name="see-also"></a>Viz také
 [Upozornění na udržovatelnost](../code-quality/maintainability-warnings.md) při [Měření složitosti a udržovatelnosti spravovaného kódu](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md)
