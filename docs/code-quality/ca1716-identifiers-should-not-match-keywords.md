---
title: 'CA1716: Identifikátory by neměly odpovídat klíčovým slovům'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- IdentifiersShouldNotMatchKeywords
- CA1716
helpviewer_keywords:
- IdentifiersShouldNotMatchKeywords
- CA1716
ms.assetid: 900cc8a1-1089-4069-a4ce-10b109ac4fab
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d27fdd455d019532b47bc531f9f7377bacd6572e
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53828625"
---
# <a name="ca1716-identifiers-should-not-match-keywords"></a>CA1716: Identifikátory by neměly odpovídat klíčovým slovům

|||
|-|-|
|TypeName|IdentifiersShouldNotMatchKeywords|
|CheckId|CA1716|
|Kategorie|Microsoft.Naming|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina

Název oboru názvů, typ nebo člen viritual nebo rozhraní odpovídá vyhrazenému klíčovému slovu programovacího jazyka.

## <a name="rule-description"></a>Popis pravidla

Identifikátory pro obory názvů, typy a virtuální a interface členy by neměly odpovídat klíčová slova, která jsou definována jazyky cílenými na modul common language runtime. V závislosti na jazyk, ve kterém se používá a klíčové slovo chyby kompilátoru a nejednoznačnosti můžete nastavit knihovnu obtížně použitelnou.

Toto pravidlo zkontroluje proti klíčových slov v těchto jazycích:

- Visual Basic

- C#

- C++/CLI

Porovnávání se používá pro [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] klíčová slova a porovnání velká a malá písmena se používá pro jiné jazyky.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

Vyberte název, který se nezobrazí v seznamu klíčových slov.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Pokud jste se přesvědčili, že identifikátor nesmí být pro uživatele matoucí rozhraní API a, že je možné použít ve všech jazycích k dispozici v rozhraní .NET Framework knihovnu můžete potlačit upozornění tohoto pravidla.