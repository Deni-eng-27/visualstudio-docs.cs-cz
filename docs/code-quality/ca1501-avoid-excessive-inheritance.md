---
title: 'CA1501: Vyhněte se nadměrné dědičnosti | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA1501
- AvoidExcessiveInheritance
helpviewer_keywords:
- AvoidExcessiveInheritance
- CA1501
ms.assetid: 9e934746-1a4d-492a-91e4-085201abafa4
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b0f91c762a283f53970e600ff081ffa5e7b74298
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="ca1501-avoid-excessive-inheritance"></a>CA1501: Vyhněte se nadměrné dědičnosti
|||  
|-|-|  
|TypeName|AvoidExcessiveInheritance|  
|CheckId|CA1501|  
|Kategorie|Microsoft.Maintainability|  
|Narušující změna|Narušující|  
  
## <a name="cause"></a>příčina  
 Typ je více než čtyři úrovně hluboko v hierarchii dědičnosti.  
  
## <a name="rule-description"></a>Popis pravidla  
 Hluboce vnořené hierarchie typů může být obtížné sledovat, pochopit a udržovat. Toto pravidlo omezuje analýzu hierarchie ve stejném modulu.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Opravit porušení toto pravidlo, typ jsou odvozeny od základní typ, který je méně hloubkové v hierarchii dědičnosti nebo odstranit některé z mezilehlých základní typy.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Je bezpečné upozornění toto pravidlo potlačit. Kód však může být obtížné zachovat. Všimněte si, že v závislosti na tom, zda se základních typů, řešení porušení toto pravidlo vytvořit nejnovější změny. Odebrání veřejného základní typy je například narušující změně.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje typ, který porušuje pravidlo.  
  
 [!code-csharp[FxCop.Maintainability.ExcessiveInheritance#1](../code-quality/codesnippet/CSharp/ca1501-avoid-excessive-inheritance_1.cs)]
 [!code-vb[FxCop.Maintainability.ExcessiveInheritance#1](../code-quality/codesnippet/VisualBasic/ca1501-avoid-excessive-inheritance_1.vb)]