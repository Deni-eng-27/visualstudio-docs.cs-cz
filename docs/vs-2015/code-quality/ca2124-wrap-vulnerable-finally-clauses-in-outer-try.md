---
title: 'CA2124: Zabalte ohroženou klauzuli finally do vnějšího bloku try | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2124
- WrapVulnerableFinallyClausesInOuterTry
helpviewer_keywords:
- CA2124
- WrapVulnerableFinallyClausesInOuterTry
ms.assetid: 82efd224-9e60-4b88-a0f5-dfabcc49a254
caps.latest.revision: 22
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 755cce18afcad3fde621fb5a960cc780906afe51
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63385997"
---
# <a name="ca2124-wrap-vulnerable-finally-clauses-in-outer-try"></a>CA2124: Zabalte ohroženou klauzuli finally do vnějšího bloku try
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|WrapVulnerableFinallyClausesInOuterTry|
|CheckId|CA2124|
|Kategorie|Microsoft.Security|
|Narušující změna|Pevné|

## <a name="cause"></a>Příčina
 Ve verzích 1.0 a 1.1 [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)], veřejná nebo chráněná metoda obsahuje `try` / `catch` / `finally` bloku. `finally` Bloku nejspíše obnovuje stav zabezpečení a není uzavřen v `finally` bloku.

## <a name="rule-description"></a>Popis pravidla
 Toto pravidlo vyhledá `try` / `finally` bloky v kódu, který se zaměřuje na verze 1.0 a 1.1 [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] , které by mohly být vystaveny filtry škodlivý výjimek, které jsou k dispozici v zásobníku volání. Pokud dojde k citlivé operace, jako jsou zosobnění v bloku try, a je vyvolána výjimka, filtr můžete spustit před `finally` bloku. Například zosobnění to znamená, že filtr by spuštěň zosobněného uživatele. Filtry jsou aktuálně implementable pouze v jazyce Visual Basic.

> [!WARNING]
> **Poznámka:** ve verzi 2.0 a novější [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)], modul runtime automaticky chrání `try` / `catch` /  `finally` znemožní filtry škodlivý výjimek, pokud dojde k obnovení přímo v rámci metody, která obsahuje bloku výjimky.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Umístit nezabalené `try` / `finally` do vnějšího bloku try. Viz druhý příklad, který následuje. To přinutí `finally` předtím, než kód filtru.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo.

## <a name="pseudo-code-example"></a>Příklad pseudo kódu

### <a name="description"></a>Popis
 Pseudo následující kód znázorňuje, zjistí toto pravidlo.

### <a name="code"></a>Kód

```
try {
   // Do some work.
   Impersonator imp = new Impersonator("John Doe");
   imp.AddToCreditCardBalance(100);
}
finally {
   // Reset security state.
   imp.Revert();
}
```

## <a name="example"></a>Příklad
 Následující kód pseudo zobrazuje vzor, můžete použít k ochraně vašeho kódu a splňovat toto pravidlo.

```
try {
     try {
        // Do some work.
     }
     finally {
        // Reset security state.
     }
}
catch()
{
    throw;
}
```
