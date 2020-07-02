---
title: 'CA1822: označte členy jako statické | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- MarkMembersAsStatic
- CA1822
helpviewer_keywords:
- MarkMembersAsStatic
- CA1822
ms.assetid: 743f0af7-41d1-4852-8d97-af0688b31118
caps.latest.revision: 19
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 2416eb24c21ef0e61bdb6db3de66c892e1eb699f
ms.sourcegitcommit: b885f26e015d03eafe7c885040644a52bb071fae
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/30/2020
ms.locfileid: "85545337"
---
# <a name="ca1822-mark-members-as-static"></a>CA1822: Označte členy jako statické
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější dokumentaci k sadě Visual Studio naleznete v tématu [CA1822: označte členy jako statické](/visualstudio/code-quality/ca1822-mark-members-as-static).

|Položka|Hodnota|
|-|-|
|TypeName|MarkMembersAsStatic|
|CheckId|CA1822|
|Kategorie|Microsoft. Performance|
|Narušující změna|Bez přerušení – Pokud člen není viditelný mimo sestavení, bez ohledu na změnu, kterou provedete.<br /><br /> Bez přerušení – Pokud pouze změníte člena na člen instance pomocí `this` klíčového slova.<br /><br /> Přerušení – Pokud změníte člena z instance členu na statický člen a je viditelný mimo sestavení.|

## <a name="cause"></a>Příčina
 Člen, který nemá přístup k datům instance, není označený jako static (Shared in [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] ).

## <a name="rule-description"></a>Popis pravidla
 Členy, kteří nemají přístup k datům instance nebo metodám instance volání, mohou být označeny jako statické (sdílené v rámci [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] ). Po označení metod jako statických bude kompilátor generovat těmto členům nevirtuální místa volání. Vygenerování nevirtuálních lokalit volání zabrání v běhu kontrolu za běhu pro každé volání, které zajistí, že aktuální ukazatel na objekt je jiný než null. To může dosáhnout měřitelného nárůstu výkonu pro kód citlivý na výkon. V některých případech představuje selhání přístupu k aktuální instanci objektu problém se správností.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Označte člen jako statický (nebo sdílený v [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] ) nebo použijte ' this '/' já ' v těle metody, pokud je to vhodné.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Z tohoto pravidla je bezpečné potlačit upozornění pro dříve dodaný kód, pro který by došlo k zásadní změně této opravy.

## <a name="related-rules"></a>Související pravidla
 [CA1811: Vyhněte se nevolanému privátnímu kódu](../code-quality/ca1811-avoid-uncalled-private-code.md)

 [CA1812: Vyhněte se nevytvořeným instancím interních tříd](../code-quality/ca1812-avoid-uninstantiated-internal-classes.md)

 [CA1804: Odeberte nepoužívané lokální hodnoty](../code-quality/ca1804-remove-unused-locals.md)
