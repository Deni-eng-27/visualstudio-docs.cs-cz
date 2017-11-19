---
title: "CA1008: Výčty by měly mít nulovou hodnotu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1008
- EnumsShouldHaveZeroValue
helpviewer_keywords:
- CA1008
- EnumsShouldHaveZeroValue
ms.assetid: 3503a73c-360c-416d-8ee4-c2aa44365a05
caps.latest.revision: "21"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 84c43a95cd607a13a302e2247cacb091a39a3070
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="ca1008-enums-should-have-zero-value"></a>CA1008: Výčty by měly mít nulovou hodnotu
|||  
|-|-|  
|TypeName|EnumsShouldHaveZeroValue|  
|CheckId|CA1008|  
|Kategorie|Microsoft.Design|  
|Narušující změna|Bez ukončování – Pokud se výzva k přidání **žádné** hodnotu výčtu bez příznaku. Pozastavení – při zobrazení výzvy k přejmenujte nebo odeberte všechny hodnoty výčtu.|  
  
## <a name="cause"></a>příčina  
 Výčet bez použité <xref:System.FlagsAttribute?displayProperty=fullName> nedefinuje člena, který má hodnotu nula; nebo výčet, který má použité <xref:System.FlagsAttribute> definuje člena s hodnotou nula, ale jeho název není 'None' nebo výčtu definuje více s hodnotou nula. členy.  
  
## <a name="rule-description"></a>Popis pravidla  
 Výchozí hodnota Neinicializovaný výčtu, stejně jako jiné typy hodnot je nula. Na jiné příznaky označené výčet měli definovat člena, který má hodnotu nula, aby výchozí hodnota je platná hodnota výčtu. V případě potřeby název člena 'None'. Přiřaďte, jinak hodnota nula se nejčastěji používaných členem. Všimněte si, ve výchozím nastavení, pokud hodnota prvního člena výčtu není nastavena v deklaraci, jeho hodnota je nula.  
  
 Pokud výčet, který má <xref:System.FlagsAttribute> použít definuje člena s hodnotou nula, jeho název by měl být 'None' indikující, že byly nastaveny žádné hodnoty ve výčtu. Použití člena s hodnotou nula k žádným jiným účelem bylo v rozporu s použití <xref:System.FlagsAttribute> v tom, že AND a nebo bitové operátory jsou nepoužitelná se členem. To znamená, že pouze jeden člen by se měla přiřadit hodnotu nula. Všimněte si, že pokud více členů, které mají hodnotu nula dojít ve výčtu s atributy příznaky `Enum.ToString()` vrátí nesprávné výsledky pro členy, kteří nejsou nula.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení tohoto pravidla pro jiné příznaky označené výčty, definujte člena, který má hodnotu 0; Jedná se o pevné změnu. Pro výčty s atributy příznaky, které definují člena s hodnotou nula název tohoto člena 'None' a odstranit všechny členy, které mají hodnotu 0; Toto je narušující změně.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Není potlačit upozornění na toto pravidlo s výjimkou výčty s atributy příznaky, které byly dříve součástí.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje dva výčty, které splňují pravidla a výčet, `BadTraceOptions`, která porušuje pravidlo.  
  
 [!code-cpp[FxCop.Design.EnumsZeroValue#1](../code-quality/codesnippet/CPP/ca1008-enums-should-have-zero-value_1.cpp)]
 [!code-csharp[FxCop.Design.EnumsZeroValue#1](../code-quality/codesnippet/CSharp/ca1008-enums-should-have-zero-value_1.cs)]
 [!code-vb[FxCop.Design.EnumsZeroValue#1](../code-quality/codesnippet/VisualBasic/ca1008-enums-should-have-zero-value_1.vb)]  
  
## <a name="related-rules"></a>Související pravidla  
 [CA2217: Neoznačujte výčty pomocí FlagsAttribute](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)  
  
 [CA1700: Nepojmenovávejte hodnoty výčtu 'Reserved'](../code-quality/ca1700-do-not-name-enum-values-reserved.md)  
  
 [CA1712: Nezadávejte na hodnoty výčtu s názvem typu](../code-quality/ca1712-do-not-prefix-enum-values-with-type-name.md)  
  
 [CA1028: Úložiště výčtu by měl být Int32](../code-quality/ca1028-enum-storage-should-be-int32.md)  
  
 [CA1027: Označte výčty pomocí FlagsAttribute](../code-quality/ca1027-mark-enums-with-flagsattribute.md)  
  
## <a name="see-also"></a>Viz také  
 <xref:System.Enum?displayProperty=fullName>