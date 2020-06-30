---
title: 'CA1413: Vyhněte se neveřejným polím v viditelných hodnotových typech COM | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1413
- AvoidNonpublicFieldsInComVisibleValueTypes
helpviewer_keywords:
- CA1413
- AvoidNonpublicFieldsInComVisibleValueTypes
ms.assetid: 1352e7eb-fefc-4239-8847-25edc7804a54
caps.latest.revision: 17
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 1054330b26cf145ebcbc943a56dc699fe793999f
ms.sourcegitcommit: b885f26e015d03eafe7c885040644a52bb071fae
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/30/2020
ms.locfileid: "85548457"
---
# <a name="ca1413-avoid-non-public-fields-in-com-visible-value-types"></a>CA1413: Vyhněte se neveřejným polím v typech hodnot viditelných modulem COM
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|Položka|Hodnota|
|-|-|
|TypeName|AvoidNonpublicFieldsInComVisibleValueTypes|
|CheckId|CA1413|
|Kategorie|Microsoft. interoperabilita|
|Narušující změna|Narušující|

## <a name="cause"></a>Příčina
 Typ hodnoty, který je konkrétně označen jako viditelný pro model COM (Component Object Model), deklaruje pole instance NonPublic.

## <a name="rule-description"></a>Popis pravidla
 Neveřejná pole instancí hodnotových typů viditelných moduly COM jsou viditelná klientům typu COM. Projděte si obsah pole s informacemi, které by neměly být vystavené nebo které budou mít neúmyslný návrh nebo bezpečnostní účinek.

 Ve výchozím nastavení jsou všechny typy veřejné hodnoty viditelné modelu COM. Chcete-li však omezit falešně pozitivní hodnoty, toto pravidlo vyžaduje explicitní stanovení viditelnosti typu modelu COM. Obsahující sestavení musí být označeno <xref:System.Runtime.InteropServices.ComVisibleAttribute?displayProperty=fullName> nastavením na `false` a typ musí být označen <xref:System.Runtime.InteropServices.ComVisibleAttribute> nastavením na `true` .

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla a nechat pole skryté, změňte typ hodnoty na typ odkazu nebo odeberte <xref:System.Runtime.InteropServices.ComVisibleAttribute> atribut z typu.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Je bezpečné potlačit upozornění od tohoto pravidla, pokud je veřejná expozice pole přijatelná.

## <a name="example"></a>Příklad
 Následující příklad ukazuje typ, který je v rozporu s pravidlem.

 [!code-csharp[FxCop.Interoperability.NonpublicField#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Interoperability.NonpublicField/cs/FxCop.Interoperability.NonpublicField.cs#1)]
 [!code-vb[FxCop.Interoperability.NonpublicField#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Interoperability.NonpublicField/vb/FxCop.Interoperability.NonpublicField.vb#1)]

## <a name="related-rules"></a>Související pravidla
 [CA1407: Vyhněte se statickým členům ve viditelných typech modelu COM](../code-quality/ca1407-avoid-static-members-in-com-visible-types.md)

 [CA1017: Označte sestavení pomocí ComVisibleAttribute](../code-quality/ca1017-mark-assemblies-with-comvisibleattribute.md)

## <a name="see-also"></a>Viz také
 [Spolupráce s nespravovaným kódem](https://msdn.microsoft.com/library/ccb68ce7-b0e9-4ffb-839d-03b1cd2c1258) [opravňující typy .NET pro spolupráci](https://msdn.microsoft.com/library/4b8afb52-fb8d-4e65-b47c-fd82956a3cdd)
