---
title: 'CA2112: Zabezpečené typy by neměly vystavovat pole'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2112
- SecuredTypesShouldNotExposeFields
helpviewer_keywords:
- SecuredTypesShouldNotExposeFields
- CA2112
ms.assetid: 9eb13a78-3487-49f2-81d1-3c3866db132f
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9784ec48193ae580d7ed41cb745f0befb1f1fde9
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="ca2112-secured-types-should-not-expose-fields"></a>CA2112: Zabezpečené typy by neměly vystavovat pole
|||
|-|-|
|TypeName|SecuredTypesShouldNotExposeFields|
|CheckId|CA2112|
|Kategorie|Microsoft.Security|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Typ veřejné nebo chráněného obsahuje veřejná pole a zabezpečené [požadavky propojení](/dotnet/framework/misc/link-demands).

## <a name="rule-description"></a>Popis pravidla
 Pokud má kód přístup k instanci typu, která je zabezpečena pomocí požadavku na propojení, nemusí kód vyhovět požadavku na propojení pro přístup k polím tohoto typu.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení toto pravidlo, zkontrolujte pole neveřejní a přidejte veřejné vlastnosti nebo metody, které vrací pole data. Kontrola zabezpečení LinkDemand na typech chránit přístup k vlastnosti a metody typ. Zabezpečení přístupu kódu, ale nevztahuje na pole.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Pro problémy se zabezpečením i pro dobrý návrh by měl opravit porušení tím, že nonpublic veřejná pole. Upozornění od tohoto pravidla můžete potlačit, pokud toto pole neobsahuje informace, které by měla zůstat zabezpečené a jste nespoléhejte na obsah tohoto pole.

## <a name="example"></a>Příklad
 V následujícím příkladu se skládá z knihovny typů (`SecuredTypeWithFields`) s zabezpečená pole typu (`Distributor`), můžete vytvořit instanci typu knihovny chybné předává instance na typy nemáte oprávnění k jejich vytvoření a kódu aplikace, která pole instancí mohou přečíst, i když nemá oprávnění, které slouží k zabezpečení typu.

 Následující kód knihovny porušuje pravidlo.

 [!code-csharp[FxCop.Security.LinkDemandOnField#1](../code-quality/codesnippet/CSharp/ca2112-secured-types-should-not-expose-fields_1.cs)]

## <a name="example"></a>Příklad
 Aplikaci nelze vytvořit instanci kvůli vyžádání odkaz, který chrání zabezpečené typu. Následující třídy umožňuje aplikaci získat instanci zabezpečené typu.

 [!code-csharp[FxCop.Security.LDOnFieldsDistributor#1](../code-quality/codesnippet/CSharp/ca2112-secured-types-should-not-expose-fields_2.cs)]

## <a name="example"></a>Příklad
 Následující aplikace ukazuje, jak, bez oprávnění k přístupu k zabezpečeným typ metody, kód můžete přistupovat k jeho pole.

 [!code-csharp[FxCop.Security.TestLinkDemandOnFields#1](../code-quality/codesnippet/CSharp/ca2112-secured-types-should-not-expose-fields_3.cs)]

 Tento příklad vytvoří následující výstup.

 **Vytvoření instance SecuredTypeWithFields. ** 
 **Zabezpečené typ pole: 22, 33**
**změna zabezpečené typ pole... ** 
 **Pole objektů do mezipaměti: 99, 33**
## <a name="related-rules"></a>Související pravidla
 [CA1051: Nedeklarujte viditelná pole instance](../code-quality/ca1051-do-not-declare-visible-instance-fields.md)

## <a name="see-also"></a>Viz také
 [Požadavky na propojení](/dotnet/framework/misc/link-demands) [Data a modelování](/dotnet/framework/data/index)