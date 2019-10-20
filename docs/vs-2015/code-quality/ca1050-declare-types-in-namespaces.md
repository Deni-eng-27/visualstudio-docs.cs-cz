---
title: 'CA1050: deklarujte typy v oborech názvů | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1050
- DeclareTypesInNamespaces
helpviewer_keywords:
- DeclareTypesInNamespaces
- CA1050
ms.assetid: 1002748d-ac8d-404f-85dd-7a12d1ad3e05
caps.latest.revision: 17
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: c56de70daeabd05215f68024339d5855686d529b
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/19/2019
ms.locfileid: "72653835"
---
# <a name="ca1050-declare-types-in-namespaces"></a>CA1050: Deklarujte typy v oborech názvů
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|DeclareTypesInNamespaces|
|CheckId|CA1050|
|Kategorie|Microsoft. Design|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Veřejný nebo chráněný typ je definován mimo rozsah pojmenovaného oboru názvů.

## <a name="rule-description"></a>Popis pravidla
 Typy jsou deklarovány v oborech názvů, aby se zabránilo kolizím názvů a jako způsob uspořádání souvisejících typů v hierarchii objektů. Typy, které jsou mimo libovolný pojmenovaný obor názvů, jsou v globálním oboru názvů, na který nelze odkazovat v kódu.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, umístěte typ do oboru názvů.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 I když nikdy nemusíte potlačit upozornění z tohoto pravidla, je bezpečné to provést, pokud sestavení nebude nikdy použito společně s jinými sestaveními.

## <a name="example"></a>Příklad
 Následující příklad ukazuje knihovnu, která má nesprávně deklarovaný typ mimo obor názvů a typ, který má stejný název deklarovaný v oboru názvů.

 [!code-csharp[FxCop.Design.TypesLiveInNamespaces#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.TypesLiveInNamespaces/cs/FxCop.Design.TypesLiveInNamespaces.cs#1)]
 [!code-vb[FxCop.Design.TypesLiveInNamespaces#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.TypesLiveInNamespaces/vb/FxCop.Design.TypesLiveInNamespaces.vb#1)]

## <a name="example"></a>Příklad
 Následující aplikace používá knihovnu, která byla definována dříve. Všimněte si, že typ deklarovaný mimo obor názvů je vytvořen, pokud název `Test` není kvalifikován oborem názvů. Všimněte si také, že pro přístup k typu `Test` v `Goodspace` je požadován název oboru názvů.

 [!code-csharp[FxCop.Design.TestTypesLive#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.TestTypesLive/cs/FxCop.Design.TestTypesLive.cs#1)]
 [!code-vb[FxCop.Design.TestTypesLive#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.TestTypesLive/vb/FxCop.Design.TestTypesLive.vb#1)]
