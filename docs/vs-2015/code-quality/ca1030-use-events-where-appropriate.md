---
title: 'CA1030: Použití událostí, kde je to vhodné | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- UseEventsWhereAppropriate
- CA1030
helpviewer_keywords:
- CA1030
- UseEventsWhereAppropriate
ms.assetid: ea051367-deeb-40f9-9b65-eb818f1e133a
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 9d00db6f9a00a273198cc50704d65ed6d2e4bb33
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60072094"
---
# <a name="ca1030-use-events-where-appropriate"></a>CA1030: Použijte události, kde je to vhodné
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|UseEventsWhereAppropriate|
|CheckId|CA1030|
|Kategorie|Microsoft.Design|
|Narušující změna|Nenarušující|

## <a name="cause"></a>Příčina
 Metoda public, protected nebo private název začíná na jednu z následujících akcí:

- Doplněk

- RemoveOn

- Oheň

- Raise

## <a name="rule-description"></a>Popis pravidla
 Toto pravidlo zjišťuje metody, které mají názvy obvykle používané pro události. Události podle návrhový vzor pozorovatel nebo publikování a odběru; používají se při změně stavu do jednoho objektu musí sdělí další objekty. Pokud metoda volána jako odpověď jednoznačně definovanou změnu stavu, by měl vyvolat metodu obslužné rutiny události. Objekty volající tuto metodu by měly místo přímého volání metody vyvolat událost.

 Některé běžné příklady událostí, které se nacházejí v uživatelských rozhraní aplikací, kde způsobí, že akce uživatele, jako je kliknutí na tlačítko segment kódu k provedení. [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] Model událostí není omezena pouze na uživatelské rozhraní, měla by se používat kdekoli musí komunikovat, stav se změní na jeden nebo více objektů.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Pokud metoda je volána při změně stavu objektu, měli byste zvážit změnu návrhu a použít [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] model událostí.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Potlačit upozornění tohoto pravidla, pokud metoda nefunguje s [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] model událostí.
