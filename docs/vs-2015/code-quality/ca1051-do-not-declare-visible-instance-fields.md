---
title: 'CA1051: Nedeklarujte viditelná pole instance | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1051
- DoNotDeclareVisibleInstanceFields
helpviewer_keywords:
- CA1051
- DoNotDeclareVisibleInstanceFields
ms.assetid: 2805376c-824c-462c-81d1-c51aaf7cabe7
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 96e518977e12f2ae061d5ab73803d51dad733149
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65686821"
---
# <a name="ca1051-do-not-declare-visible-instance-fields"></a>CA1051: Nedeklarujte viditelná pole instance
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|DoNotDeclareVisibleInstanceFields|
|CheckId|CA1051|
|Kategorie|Microsoft.Design|
|Narušující změna|Narušující|

## <a name="cause"></a>Příčina
 Externě viditelný typ obsahuje pole instance externě viditelné.

## <a name="rule-description"></a>Popis pravidla
 Hlavní použití pole by mělo být jako podrobnost implementace. Pole by měla být `private` nebo `internal` a měla by být vystavena s použitím vlastností. Je snadné přístup k vlastnosti, jako je přístup k poli a kód v přistupující objekty vlastnosti můžete změnit, protože funkce typu rozbalte bez vnášení rozbíjející změny. Vlastnosti, které právě vracejí hodnotu privátní nebo interní pole jsou optimalizována pro provedení ji přístup k poli. velmi malé zvýšení výkonu je spojené s použitím externě viditelné pole prostřednictvím vlastností.

 Externě viditelný odkazuje na `public`, `protected`, a `protected internal` (`Public`, `Protected`, a `Protected Friend` v jazyce Visual Basic) úrovní přístupu.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, ujistěte se, pole `private` nebo `internal` a zpřístupnit ji pomocí externě viditelné vlastnosti.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo. Externě viditelné pole neposkytují žádné výhody, které nejsou k dispozici pro vlastnosti. Kromě toho veřejné polí se nedají chránit pomocí [požadavky propojení](https://msdn.microsoft.com/library/a33fd5f9-2de9-4653-a4f0-d9df25082c4d). Zobrazit [CA2112: Zabezpečené typy by neměly vystavovat pole](../code-quality/ca2112-secured-types-should-not-expose-fields.md).

## <a name="example"></a>Příklad
 Následující příklad ukazuje typ (`BadPublicInstanceFields`), který porušuje tato pravidla. `GoodPublicInstanceFields` zobrazuje opravený kód.

 [!code-csharp[FxCop.Design.TypesPublicInstanceFields#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.TypesPublicInstanceFields/cs/FxCop.Design.TypesPublicInstanceFields.cs#1)]

## <a name="related-rules"></a>Související pravidla
 [CA2112: Zabezpečené typy by neměly vystavovat pole](../code-quality/ca2112-secured-types-should-not-expose-fields.md)

## <a name="see-also"></a>Viz také
 [Požadavky propojení](https://msdn.microsoft.com/library/a33fd5f9-2de9-4653-a4f0-d9df25082c4d)
