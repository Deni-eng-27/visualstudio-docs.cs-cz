---
title: 'CA1716: Identifikátory by neměly odpovídat klíčová slova | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
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
ms.openlocfilehash: c695f66a096614621cee2f38aed3e8fd6d970bed
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="ca1716-identifiers-should-not-match-keywords"></a>CA1716: Identifikátory by neměly odpovídat klíčovým slovům
|||  
|-|-|  
|TypeName|IdentifiersShouldNotMatchKeywords|  
|CheckId|CA1716|  
|Kategorie|Microsoft.Naming|  
|Narušující změna|Narušující|  
  
## <a name="cause"></a>příčina  
 Název oboru názvů, typ nebo člen viritual nebo rozhraní odpovídá rezervované klíčové slovo v programovacím jazyce.  
  
## <a name="rule-description"></a>Popis pravidla  
 Identifikátory pro obory názvů, typy a virtuální a členové rozhraní by neměly odpovídat klíčová slova, která jsou definovaná sadou jazyky, které cílí modul common language runtime. V závislosti na jazyk, který se používá a klíčové slovo chyby kompilátoru a nejednoznačnosti můžete nastavit knihovny obtížně použitelný.  
  
 Toto pravidlo zkontroluje proti klíčová slova v těchto jazycích:  
  
-   Visual Basic  
  
-   C#  
  
-   C++/CLI  
  
 Porovnávání se používá pro [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] klíčová slova a porovnání malá a velká písmena se používá pro jiné jazyky.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Vyberte název, který se nenachází v seznamu klíčová slova.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Upozornění od tohoto pravidla můžete potlačit, pokud jste přesvědčeni, že identifikátor nesmí být pro uživatele matoucí rozhraní API, a že je použitelná ve všech jazycích k dispozici v knihovně [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)].