---
title: 'CA1500: Názvy proměnných by neměly odpovídat názvům polí'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- VariableNamesShouldNotMatchFieldNames
- CA1500
helpviewer_keywords:
- VariableNamesShouldNotMatchFieldNames
- CA1500
ms.assetid: fa0e5029-79e9-4a33-8576-787ac3c26c39
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 3f7e8b0021fc3c318389aa3d6d3f53391b71351f
ms.sourcegitcommit: 485ffaedb1ade71490f11cf05962add1718945cc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/16/2019
ms.locfileid: "72443963"
---
# <a name="ca1500-variable-names-should-not-match-field-names"></a>CA1500: Názvy proměnných by neměly odpovídat názvům polí

|||
|-|-|
|TypeName|VariableNamesShouldNotMatchFieldNames|
|CheckId|CA1500|
|Kategorie|Microsoft. udržovatelnost|
|Zásadní změna|Při vyvolání pro parametr, který má stejný název jako pole:<br /><br /> -Bez přerušení – Pokud se pole i metoda, která deklaruje parametr, nemůže zobrazit mimo sestavení, bez ohledu na změnu, kterou provedete.<br />-Rozdělení – Pokud změníte název pole a lze jej zobrazit mimo sestavení.<br />– Při změně názvu parametru a metody, která ji deklaruje, lze zobrazit mimo sestavení.<br /><br /> Při vyvolání pro místní proměnnou, která má stejný název jako pole:<br /><br /> -Bez přerušení – Pokud se pole nemůže zobrazit mimo sestavení, bez ohledu na změnu, kterou provedete.<br />-Nerušit – Pokud změníte název místní proměnné a nezměníte název tohoto pole.<br />-Rozdělení – Pokud změníte název pole a může se zobrazit mimo sestavení.|

## <a name="cause"></a>příčina

Metoda instance deklaruje parametr nebo místní proměnnou, jejíž název odpovídá poli instance deklarující typu. Pro zachycení místních proměnných, které porušují pravidlo, musí být testované sestavení sestaveno pomocí ladicích informací a přidružený soubor databáze programu (PDB) musí být k dispozici.

## <a name="rule-description"></a>Popis pravidla

Když název pole instance odpovídá parametru nebo názvu místní proměnné, je k poli instance přistupovaná pomocí klíčového slova `this` (`Me` v [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]) v těle metody. Při údržbě kódu je snadné tento rozdíl zapomenout a předpokládat, že parametr nebo místní proměnná odkazují na pole instance, které vede k chybám. To je užitečné hlavně v případě dlouhých těla metod.

## <a name="how-to-fix-violations"></a>Jak opravit porušení

Chcete-li opravit porušení tohoto pravidla, přejmenujte buď parametr nebo proměnnou, nebo pole.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Nepotlačujte upozornění na toto pravidlo.

## <a name="example"></a>Příklad

Následující příklad ukazuje dvě porušení pravidla.

[!code-vb[FxCop.Maintainability.VarMatchesField#1](../code-quality/codesnippet/VisualBasic/ca1500-variable-names-should-not-match-field-names_1.vb)]
[!code-csharp[FxCop.Maintainability.VarMatchesField#1](../code-quality/codesnippet/CSharp/ca1500-variable-names-should-not-match-field-names_1.cs)]
