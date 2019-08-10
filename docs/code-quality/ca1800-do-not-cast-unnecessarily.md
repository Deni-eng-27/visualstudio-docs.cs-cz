---
title: 'CA1800: Nepřetypujte zbytečně'
ms.date: 10/26/2017
ms.topic: reference
f1_keywords:
- CA1800
- DoNotCastUnnecessarily
helpviewer_keywords:
- DoNotCastUnnecessarily
- CA1800
ms.assetid: b79a010a-6627-421e-8955-6007e32fa808
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- VB
- CSharp
ms.workload:
- multiple
ms.openlocfilehash: 942a9911d0dadbf5f130344735ca9aa504cb71fd
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68921586"
---
# <a name="ca1800-do-not-cast-unnecessarily"></a>CA1800: Nepřetypujte zbytečně

|||
|-|-|
|TypeName|DoNotCastUnnecessarily|
|CheckId|CA1800|
|Kategorie|Microsoft. Performance|
|Narušující změna|Nenarušující|

## <a name="cause"></a>příčina
Metoda provádí duplicitní přetypování na jednom z jeho argumentů nebo místních proměnných.

Pro úplnou analýzu podle tohoto pravidla musí být testované sestavení sestaveno pomocí ladicích informací a přidružený soubor databáze programu (PDB) musí být k dispozici.

## <a name="rule-description"></a>Popis pravidla
Duplicitní přetypování snižuje výkon, zvláště když jsou přetypování vykonána v příkazech kompaktní iterace. U explicitních operací přetypování uložte výsledek přetypování do místní proměnné a místo duplicitních operací přetypování použijte místní proměnnou.

Pokud operátor slouží k otestování, zda bude přetypování úspěšné před samotným přetypováním, zvažte místo toho testování výsledku `as` operátoru. `is` C# To poskytuje stejnou funkčnost bez operace implicitního přetypování, kterou provádí `is` operátor. Nebo v C# 7,0 a novějším, použijte `is` operátor s porovnáváním [vzorů](/dotnet/csharp/language-reference/keywords/is#pattern-matching-with-is) pro kontrolu převodu typu a přetypujte výraz na proměnnou daného typu v jednom kroku.

## <a name="how-to-fix-violations"></a>Jak opravit porušení
Chcete-li opravit porušení tohoto pravidla, upravte implementaci metody tak, aby minimalizovala počet operací přetypování.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
Z tohoto pravidla je bezpečné potlačit upozornění nebo pravidlo ignorovat, pokud výkon nezáleží na výkonu.

## <a name="examples"></a>Příklady
Následující příklad ukazuje metodu, která porušuje pravidlo pomocí C# `is` operátoru. Druhá metoda splňuje pravidlo tím, že nahrazuje `is` operátor s testem proti výsledku `as` operátoru, což snižuje počet operací přetypování na iteraci od dvou k jednomu. Třetí metoda také splňuje pravidlo pomocí `is` [porovnávání vzorů](/dotnet/csharp/language-reference/keywords/is#pattern-matching-with-is) pro vytvoření proměnné požadovaného typu, pokud by převod typu proběhl úspěšně.

[!code-csharp[FxCop.Performance.UnnecessaryCastsAsIs#1](../code-quality/codesnippet/CSharp/ca1800-do-not-cast-unnecessarily_1.cs)]

Následující příklad ukazuje metodu, `start_Click`, která má více duplicitní explicitní přetypování, které porušují pravidlo a metodu, `reset_Click`která splňuje pravidlo uložením přetypování do místní proměnné.

[!code-vb[FxCop.Performance.UnnecessaryCasts#1](../code-quality/codesnippet/VisualBasic/ca1800-do-not-cast-unnecessarily_2.vb)]
[!code-csharp[FxCop.Performance.UnnecessaryCasts#1](../code-quality/codesnippet/CSharp/ca1800-do-not-cast-unnecessarily_2.cs)]

## <a name="see-also"></a>Viz také:

- [as (C# referenční)](/dotnet/csharp/language-reference/keywords/as)
- [je (C# referenční)](/dotnet/csharp/language-reference/keywords/is)