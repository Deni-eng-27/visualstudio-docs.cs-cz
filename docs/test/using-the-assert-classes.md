---
title: MSTest, třídy a metody kontrolního výrazu
ms.date: 06/07/2018
ms.topic: reference
helpviewer_keywords:
- Assert classes
- Assert methods
- unit tests, Assert classes
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
author: mikejo5000
ms.openlocfilehash: c36916c79bd783ed2c6ce960b068e85478b9971d
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "75592045"
---
# <a name="use-assert-classes-for-unit-testing"></a>Použití tříd Assert pro testování částí

<xref:Microsoft.VisualStudio.TestTools.UnitTesting>Pro ověření konkrétních funkcí použijte třídy Assert oboru názvů. Metoda testování částí zpracuje kód metody v kódu vaší aplikace, ale oznámí správnost chování kódu pouze v případě, že zahrnete příkazy Assert.

## <a name="kinds-of-asserts"></a>Druhy kontrolních výrazů

<xref:Microsoft.VisualStudio.TestTools.UnitTesting>Obor názvů poskytuje několik druhů kontrolních tříd.

V testovací metodě můžete volat libovolné metody <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert?displayProperty=fullName> třídy, například <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.AreEqual%2A?displayProperty=nameWithType> . <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert>Třída obsahuje mnoho metod, ze kterých si můžete vybrat, a mnohé z metod mají několik přetížení.

### <a name="compare-strings-and-collections"></a>Porovnávání řetězců a kolekcí

Použijte <xref:Microsoft.VisualStudio.TestTools.UnitTesting.CollectionAssert> třídu pro porovnání kolekcí objektů nebo pro ověření stavu kolekce.

Použijte <xref:Microsoft.VisualStudio.TestTools.UnitTesting.StringAssert> třídu k porovnání a prohlédnutí řetězců. Tato třída obsahuje nejrůznější užitečné metody, jako například <xref:Microsoft.VisualStudio.TestTools.UnitTesting.StringAssert.Contains%2A?displayProperty=nameWithType> , <xref:Microsoft.VisualStudio.TestTools.UnitTesting.StringAssert.Matches%2A?displayProperty=nameWithType> a <xref:Microsoft.VisualStudio.TestTools.UnitTesting.StringAssert.StartsWith%2A?displayProperty=nameWithType> .

### <a name="exceptions"></a>Výjimky

<xref:Microsoft.VisualStudio.TestTools.UnitTesting.AssertFailedException>Výjimka je vyvolána pokaždé, když se test nezdařil. Test se nezdařil, pokud vyprší časový limit, vyvolá neočekávanou výjimku nebo obsahuje příkaz kontrolního výrazu, který vytváří výsledek **neúspěchu** .

<xref:Microsoft.VisualStudio.TestTools.UnitTesting.AssertInconclusiveException>Je vyvolána, když test vygeneruje výsledek **neprůkazné**. Obvykle přidáte <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.Inconclusive%2A?displayProperty=nameWithType> příkaz do testu, na kterém stále pracujete, abyste označili, že ještě není připravené ke spuštění.

> [!NOTE]
> Alternativním strategií je označit test, který není připraven ke spuštění s <xref:Microsoft.VisualStudio.TestTools.UnitTesting.IgnoreAttribute> atributem. To však má nevýhodu, že nemůžete snadno generovat sestavu pro počet testů, které nejsou implementovány.

Pokud zapíšete novou třídu výjimky kontrolního výrazu, dědí ze základní třídy, <xref:Microsoft.VisualStudio.TestTools.UnitTesting.UnitTestAssertException> aby byla výjimka rozpoznána jako selhání kontrolního výrazu namísto neočekávané výjimky vyvolané z vašeho testovacího nebo produkčního kódu.

Chcete-li ověřit, že výjimka, kterou očekáváte vyvolat metodou v kódu aplikace, je ve skutečnosti vyvolána, použijte <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A?displayProperty=nameWithType> metodu.

## <a name="see-also"></a>Viz také

- [Testování částí kódu](../test/unit-test-your-code.md)
