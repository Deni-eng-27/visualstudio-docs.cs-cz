---
title: "CA1802: Použijte literály, kde je to vhodné | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- UseLiteralsWhereAppropriate
- CA1802
helpviewer_keywords:
- UseLiteralsWhereAppropriate
- CA1802
ms.assetid: 2515e4cd-9e61-486d-b067-58ba1a743ce4
caps.latest.revision: "17"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 66ee20e099de0206664390623b7a50c5fec723a1
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="ca1802-use-literals-where-appropriate"></a>CA1802: Použijte literály, kde je to vhodné
|||  
|-|-|  
|TypeName|UseLiteralsWhereAppropriate|  
|CheckId|CA1802|  
|Kategorie|Microsoft.Performance|  
|Narušující změna|Nenarušující|  
  
## <a name="cause"></a>příčina  
 Pole je deklarovaná `static` a `readonly` (`Shared` a `ReadOnly` v [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]) a je inicializovaný s hodnotou, která je computable v době kompilace.  
  
## <a name="rule-description"></a>Popis pravidla  
 Hodnota `static``readonly` pole se vypočítává za běhu, při volání statického konstruktoru pro deklarující typ. Pokud `static``readonly` pole je inicializováno, když je deklarován a statického konstruktoru není deklarovaný explicitně, kompilátor vydává statického konstruktoru k chybě při inicializaci pole.  
  
 Hodnota `const` pole je počítaný v době kompilace a uložená v metadatech, což zvyšuje výkon modulu runtime srovnání s `static``readonly` pole.  
  
 Hodnota přiřazená k cílové pole je computable v době kompilace, změnou deklaraci k `const` pole tak, aby hodnota je vypočítána v době kompilace místo v době běhu.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li porušení toto pravidlo, nahraďte `static` a `readonly` modifikátory s `const` modifikátor.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Je bezpečné upozornění toto pravidlo potlačit, nebo zakázat pravidlo, pokud výkon není zájmu.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje typu, `UseReadOnly`, která porušuje pravidlo a typu, `UseConstant`, která by splnila pravidlo.  
  
 [!code-vb[FxCop.Performance.UseLiterals#1](../code-quality/codesnippet/VisualBasic/ca1802-use-literals-where-appropriate_1.vb)]
 [!code-csharp[FxCop.Performance.UseLiterals#1](../code-quality/codesnippet/CSharp/ca1802-use-literals-where-appropriate_1.cs)]