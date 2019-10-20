---
title: 'CA1721: názvy vlastností by neměly odpovídat metodám Get | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1721
- PropertyNamesShouldNotMatchGetMethods
helpviewer_keywords:
- CA1721
- PropertyNamesShouldNotMatchGetMethods
ms.assetid: 45a0e853-1f06-4688-af1b-cc634409e295
caps.latest.revision: 19
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 366932c83328c6810e0103308db1c73a3e3076cb
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/19/2019
ms.locfileid: "72671612"
---
# <a name="ca1721-property-names-should-not-match-get-methods"></a>CA1721: Názvy vlastností by neměly odpovídat metodám Get
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|PropertyNamesShouldNotMatchGetMethods|
|CheckId|CA1721|
|Kategorie|Microsoft. pojmenování|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Název veřejného nebo chráněného člena začíná na Get a jinak odpovídá názvu vlastnosti Public nebo Protected. Například typ, který obsahuje metodu s názvem GetColor a vlastnost s názvem Color, porušuje toto pravidlo.

## <a name="rule-description"></a>Popis pravidla
 Metody Get a vlastnosti by měly mít názvy, které zřetelně rozliší jejich funkce.

 Zásady vytváření názvů poskytují běžný vzhled pro knihovny, které cílí na modul CLR (Common Language Runtime). Tím se zkracuje čas potřebný k učení nové softwarové knihovny a zvyšuje se důvěra zákazníků, že knihovna byla vyvinutá někým, kdo má zkušenosti s vývojem spravovaného kódu.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Změňte název tak, aby se neshodoval s názvem metody, která je s předponou "Get".

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo.

> [!NOTE]
> Toto upozornění může být vyloučeno, pokud je metoda get způsobena implementací rozhraní IExtenderProvider.

## <a name="example"></a>Příklad
 Následující příklad obsahuje metodu a vlastnost, která toto pravidlo porušuje.

 [!code-csharp[FxCop.Naming.GetMethod#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Naming.GetMethod/cs/FxCop.Naming.GetMethod.cs#1)]
 [!code-vb[FxCop.Naming.GetMethod#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Naming.GetMethod/vb/FxCop.Naming.GetMethod.vb#1)]

## <a name="related-rules"></a>Související pravidla
 [CA1024: Použijte vlastnosti, kde je to vhodné](../code-quality/ca1024-use-properties-where-appropriate.md)
