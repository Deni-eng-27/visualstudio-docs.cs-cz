---
title: 'CA1809: Vyhněte se nadměrným místním hodnotám'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1809
- AvoidExcessiveLocals
helpviewer_keywords:
- AvoidExcessiveLocals
- CA1809
ms.assetid: 5c81ea43-cb49-448f-980f-a1dd9764043c
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a4790d78ae1050a2c5443a8f048416f5f4de078e
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="ca1809-avoid-excessive-locals"></a>CA1809: Vyhněte se nadměrným místním hodnotám
|||
|-|-|
|TypeName|AvoidExcessiveLocals|
|CheckId|CA1809|
|Kategorie|Microsoft.Performance|
|Narušující změna|Nenarušující|

## <a name="cause"></a>příčina
 Člen obsahuje víc než 64 místní proměnné, některé z nich může být generované kompilátorem.

## <a name="rule-description"></a>Popis pravidla
 Běžné optimalizace výkonu je pro ukládání hodnot v registru procesoru místo v paměti, což se označuje jako *enregistering* hodnota. Modul common language runtime zvažuje až 64 místní proměnné pro enregistration. Proměnné, které nejsou zpracovávány vnitřně zaregistrované daly v zásobníku a je třeba přesunout do registru před manipulaci. Chcete-li možnost povolit, aby všechny místní proměnné získat zpracovávány vnitřně zaregistrované, omezit počet místních proměnných na 64.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení toto pravidlo, Refaktorovat implementace používat více než 64 místní proměnné.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Je bezpečné upozornění toto pravidlo potlačit nebo zakážete pravidlo, pokud výkon není problém.

## <a name="related-rules"></a>Související pravidla
 [CA1804: Odeberte nepoužívané místní hodnoty](../code-quality/ca1804-remove-unused-locals.md)