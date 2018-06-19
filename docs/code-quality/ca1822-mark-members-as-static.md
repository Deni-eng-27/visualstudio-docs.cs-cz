---
title: 'CA1822: Označte členy jako statické'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- MarkMembersAsStatic
- CA1822
helpviewer_keywords:
- MarkMembersAsStatic
- CA1822
ms.assetid: 743f0af7-41d1-4852-8d97-af0688b31118
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 498a3638a02891683aff1b343431418d1a82bab0
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31914982"
---
# <a name="ca1822-mark-members-as-static"></a>CA1822: Označte členy jako statické
|||
|-|-|
|TypeName|MarkMembersAsStatic|
|CheckId|CA1822|
|Kategorie|Microsoft.Performance|
|Narušující změna|Bez ukončování – Pokud člen není zobrazen mimo sestavení, bez ohledu na změnu provedete. Pevné – Pokud změníte člen jen na instanci členu s `this` – klíčové slovo.<br /><br /> Pozastavení – Pokud změníte člen členem instance na statický člen a je viditelný mimo sestavení.|

## <a name="cause"></a>příčina
 Člena, který není přístup k datům instance není označena jako statické (sdílené v [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]).

## <a name="rule-description"></a>Popis pravidla
 Členové, které není přístup k instanci data nebo volání metody instance může být označen jako statické (sdílené v [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]). Po označení metod jako statických bude kompilátor generovat těmto členům nevirtuální místa volání. Emitování nevirtuální volání lokality zabrání kontrolu v době běhu pro každé volání, které zajišťuje, že je aktuální objekt ukazatele nesmí být nulová. To můžete dosáhnout měřitelné výkonnější pro kód náročné na výkon. V některých případech představuje selhání pro přístup k aktuální instanci objektu správnost problém.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Označit jako statický člen (nebo sdílet v [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]) nebo použít 'this' / 'Mi' v metodě body, podle potřeby.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Je bezpečné pro potlačení upozornění od tohoto pravidla pro dříve dodané kód, pro které by bylo opravu narušující změně.

## <a name="related-rules"></a>Související pravidla
 [CA1811: Vyhněte se nevolanému místnímu kódu](../code-quality/ca1811-avoid-uncalled-private-code.md)

 [CA1812: Vyhněte se nevytvořeným instancím vnitřních tříd](../code-quality/ca1812-avoid-uninstantiated-internal-classes.md)

 [CA1804: Odeberte nepoužívané místní hodnoty](../code-quality/ca1804-remove-unused-locals.md)