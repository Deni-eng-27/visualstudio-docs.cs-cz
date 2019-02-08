---
title: 'CA2134: Metody musí při přepisování základních metod zachovávat konzistentní transparentnost'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2134
ms.assetid: 3b17e487-0326-442e-90e1-dc0ba9cdd3f2
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 67114c20a7fcf5e8ff01773d8777b23d3caf3d91
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55954657"
---
# <a name="ca2134-methods-must-keep-consistent-transparency-when-overriding-base-methods"></a>CA2134: Metody musí při přepisování základních metod zachovávat konzistentní transparentnost

|||
|-|-|
|TypeName|MethodsMustOverrideWithConsistentTransparency|
|CheckId|CA2134|
|Kategorie|Microsoft.Security|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Toto pravidlo je vyvoláno, když metoda označená pomocí <xref:System.Security.SecurityCriticalAttribute> přepíše metodu, která je transparentní nebo označená <xref:System.Security.SecuritySafeCriticalAttribute>. Toto pravidlo vyvoláno, když metoda, která je transparentní nebo označená <xref:System.Security.SecuritySafeCriticalAttribute> přepíše metodu označenou atributem <xref:System.Security.SecurityCriticalAttribute>.

 Pravidlo je použito při přepisování virtuální metody nebo implementaci rozhraní.

## <a name="rule-description"></a>Popis pravidla
 Toto pravidlo je vyvoláno při pokusech změňte přístupnost zabezpečení metody dále celým řetězcem dědičnosti. Například pokud virtuální metodu v základní třídě je transparentní nebo bezpečně kritické, pak odvozené třídy musí ji přepište bezpečný a kritický nebo transparentní metoda. Naopak pokud virtuální je kritický pro zabezpečení, odvozené třídy musí přepsat ho na kritickou metodu zabezpečení. Stejné pravidlo platí i pro implementaci metody rozhraní.

 Když kód je JIT kompilaci místo za běhu, takže výpočtu transparentnosti nemá žádné informace o dynamické typu se vynucují pravidla transparentnosti. Výsledek výpočtu transparentnosti proto musí být schopen určit pouze statické typy se zkompilovaný pomocí kompilátoru JIT, bez ohledu na to dynamického typu.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, změňte průhlednost metody, která je přepisování virtuální metody nebo implementaci rozhraní tak, aby odpovídaly průhlednost virtuální nebo metodu rozhraní.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění tohoto pravidla. Porušení tohoto pravidla způsobí modul runtime <xref:System.TypeLoadException> pro sestavení, které používají transparentnosti úrovně 2.

## <a name="examples"></a>Příklady

### <a name="code"></a>Kód
 [!code-csharp[FxCop.Security.CA2134.MethodsMustOverrideWithConsistentTransparency#1](../code-quality/codesnippet/CSharp/ca2134-methods-must-keep-consistent-transparency-when-overriding-base-methods_1.cs)]

## <a name="see-also"></a>Viz také:
 [Kód transparentní pro zabezpečení, úroveň 2](/dotnet/framework/misc/security-transparent-code-level-2)