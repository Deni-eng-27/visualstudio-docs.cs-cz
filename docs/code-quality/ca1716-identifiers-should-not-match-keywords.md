---
title: 'CA1716: Identifikátory by se neměly shodovat s klíčovými slovy'
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- IdentifiersShouldNotMatchKeywords
- CA1716
helpviewer_keywords:
- IdentifiersShouldNotMatchKeywords
- CA1716
ms.assetid: 900cc8a1-1089-4069-a4ce-10b109ac4fab
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 7a3f030c9c64d975d93aa2aeee90d37f765a6a63
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/24/2019
ms.locfileid: "71234046"
---
# <a name="ca1716-identifiers-should-not-match-keywords"></a>CA1716: Identifikátory by se neměly shodovat s klíčovými slovy

|||
|-|-|
|TypeName|IdentifiersShouldNotMatchKeywords|
|CheckId|CA1716|
|Kategorie|Microsoft.Naming|
|Zásadní změna|Narušující|

## <a name="cause"></a>příčina

Název oboru názvů, typ nebo člen virtuálního nebo rozhraní odpovídá rezervovanému klíčovému slovu v programovacím jazyce.

Ve výchozím nastavení toto pravidlo vyhledává pouze externě viditelné obory názvů, typy a členy, ale je možné jej [nakonfigurovat](#configurability).

## <a name="rule-description"></a>Popis pravidla

Identifikátory pro obory názvů, typy a členy virtuálních a rozhraní by neměly odpovídat klíčovým slovům, která jsou definována jazyky, které cílí na modul CLR (Common Language Runtime). V závislosti na použitém jazyce a klíčovém slovu, chybách kompilátoru a nejednoznačnosti může být knihovna obtížné použít.

Toto pravidlo kontroluje klíčová slova v následujících jazycích:

- Visual Basic
- C#
- C++/CLI

Porovnávání bez rozlišování velkých a malých písmen se používá pro Visual Basic klíčová slova a pro ostatní jazyky se používá porovnání s rozlišováním velkých a malých písmen.

## <a name="how-to-fix-violations"></a>Jak opravit porušení

Vyberte název, který se nezobrazuje v seznamu klíčových slov.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Pokud si nejste přesvědčeni, že identifikátor Nezaměňujte uživatele rozhraní API a že je knihovna použitelná ve všech dostupných jazycích v rozhraní .NET, můžete potlačit upozornění z tohoto pravidla.

## <a name="configurability"></a>Konfigurovatelnost

Pokud toto pravidlo spouštíte z [analyzátorů FxCop](install-fxcop-analyzers.md) (a ne pomocí starší verze analýzy), můžete nakonfigurovat, které části základu kódu mají spustit toto pravidlo, na základě jejich přístupnosti. Například chcete-li určit, že pravidlo by mělo běžet pouze proti neveřejnému povrchu rozhraní API, přidejte do souboru. editorconfig v projektu následující dvojici klíč-hodnota:

```ini
dotnet_code_quality.ca1716.api_surface = private, internal
```

Tuto možnost můžete nakonfigurovat jenom pro toto pravidlo, pro všechna pravidla nebo pro všechna pravidla v této kategorii (pojmenování). Další informace najdete v tématu [Konfigurace analyzátorů FxCop](configure-fxcop-analyzers.md).