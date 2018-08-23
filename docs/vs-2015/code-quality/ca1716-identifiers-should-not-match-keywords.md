---
title: 'CA1716: Identifikátory by neměly odpovídat klíčovým slovům | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IdentifiersShouldNotMatchKeywords
- CA1716
helpviewer_keywords:
- IdentifiersShouldNotMatchKeywords
- CA1716
ms.assetid: 900cc8a1-1089-4069-a4ce-10b109ac4fab
caps.latest.revision: 23
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: f3d83fcf02f8467fe6552420146ce106677fdcfd
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42685077"
---
# <a name="ca1716-identifiers-should-not-match-keywords"></a>CA1716: Identifikátory by neměly odpovídat klíčovým slovům
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CA1716: identifikátory by neměly odpovídat klíčovým slovům](https://docs.microsoft.com/visualstudio/code-quality/ca1716-identifiers-should-not-match-keywords).  
  
TypeName | IdentifiersShouldNotMatchKeywords |  
| ID kontroly | CA1716 |  
| Kategorie | Microsoft.Naming|  
| Zásadní změna | Zásadní |  
  
## <a name="cause"></a>příčina  
 Název oboru názvů, typ nebo člen viritual nebo rozhraní odpovídá vyhrazenému klíčovému slovu programovacího jazyka.  
  
## <a name="rule-description"></a>Popis pravidla  
 Identifikátory pro obory názvů, typy a virtuální a interface členy by neměly odpovídat klíčová slova, která jsou definována jazyky cílenými na modul common language runtime. V závislosti na jazyk, ve kterém se používá a klíčové slovo chyby kompilátoru a nejednoznačnosti můžete nastavit knihovnu obtížně použitelnou.  
  
 Toto pravidlo zkontroluje proti klíčových slov v těchto jazycích:  
  
-   Visual Basic  
  
-   C#  
  
-   C++/CLI  
  
 Porovnávání se používá pro [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] klíčová slova a porovnání velká a malá písmena se používá pro jiné jazyky.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Vyberte název, který se nezobrazí v seznamu klíčových slov.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Pokud jste se přesvědčili, že identifikátor nesmí být pro uživatele matoucí rozhraní API a je použitelné ve všech jazycích k dispozici v knihovně můžete potlačit upozornění tohoto pravidla [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)].



