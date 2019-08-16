---
title: 'CA1024: Použijte vlastnosti, kde je to vhodné'
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- UsePropertiesWhereAppropriate
- CA1024
helpviewer_keywords:
- CA1024
- UsePropertiesWhereAppropriate
ms.assetid: 3a04f765-af7c-4872-87ad-9cc29e8e657f
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 2763d7dd167ad0027509c44b8f9d43523f03976b
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/16/2019
ms.locfileid: "69547791"
---
# <a name="ca1024-use-properties-where-appropriate"></a>CA1024: Použijte vlastnosti, kde je to vhodné

|||
|-|-|
|TypeName|UsePropertiesWhereAppropriate|
|CheckId|CA1024|
|Kategorie|Microsoft.Design|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina

Metoda má název, který začíná `Get`, nepřebírá žádné parametry a vrací hodnotu, která není polem.

Ve výchozím nastavení toto pravidlo vyhledává pouze veřejné a chráněné metody, ale je možné jej [nakonfigurovat](#configurability).

## <a name="rule-description"></a>Popis pravidla

Ve většině případů vlastnosti reprezentují data a metody, které provádějí akce. Vlastnosti jsou dostupné jako pole, což usnadňuje jejich použití. Metoda je dobrým kandidátem, který se stane vlastností, pokud je přítomna jedna z těchto podmínek:

- Nepřijímá žádné argumenty a vrací informace o stavu objektu.

- Přijímá jeden argument pro nastavení některých částí stavu objektu.

Vlastnosti by se měly chovat, jako by se jedná o pole. Pokud metoda nemůže, neměla by být změněna na vlastnost. Metody jsou lepší než vlastnosti v následujících situacích:

- Metoda provádí časově náročnou operaci. Metoda je vnímana pomalejší než čas, který je požadován k nastavení nebo získání hodnoty pole.

- Metoda provádí převod. Přístup k poli nevrátí převedenou verzi dat, která ukládá.

- Metoda get má pozorovatelný vedlejší efekt. Načtení hodnoty pole neprodukuje žádné vedlejší účinky.

- Pořadí spuštění je důležité. Nastavení hodnoty pole nezávisí na výskytu jiných operací.

- Volání metody dvakrát v případě úspěchu vytváří různé výsledky.

- Metoda je statická, ale vrací objekt, který může změnit volající. Načítání hodnoty pole neumožňuje volajícímu měnit data, která jsou uložena v poli.

- Metoda vrací pole.

## <a name="how-to-fix-violations"></a>Jak opravit porušení

Chcete-li opravit porušení tohoto pravidla, změňte metodu na vlastnost.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Potlačí upozornění z tohoto pravidla, pokud metoda splňuje alespoň jedno z výše uvedených kritérií.

## <a name="configurability"></a>Konfigurovatelnost

Pokud toto pravidlo spouštíte z [analyzátorů FxCop](install-fxcop-analyzers.md) (a ne pomocí starší verze analýzy), můžete nakonfigurovat, které části základu kódu mají spustit toto pravidlo, na základě jejich přístupnosti. Například chcete-li určit, že pravidlo by mělo běžet pouze proti neveřejnému povrchu rozhraní API, přidejte do souboru. editorconfig v projektu následující dvojici klíč-hodnota:

```ini
dotnet_code_quality.ca1024.api_surface = private, internal
```

Tuto možnost můžete nakonfigurovat jenom pro toto pravidlo, pro všechna pravidla nebo pro všechna pravidla v této kategorii (návrh). Další informace najdete v tématu [Konfigurace analyzátorů FxCop](configure-fxcop-analyzers.md).

## <a name="control-property-expansion-in-the-debugger"></a>Rozšíření vlastností ovládacího prvku v ladicím programu

Jedním z důvodů, proč programátoři nepoužívají vlastnost, je, že nechtějí, aby ladicí program automaticky rozbalí. Například vlastnost může zahrnovat přidělení velkého objektu nebo volání volání nespravovaného objektu, ale nemusí mít ve skutečnosti žádné pozorovatelné vedlejší účinky.

Ladicímu programu můžete zabránit v automaticky rozbalování vlastností, a <xref:System.Diagnostics.DebuggerBrowsableAttribute?displayProperty=fullName>to použitím. Následující příklad ukazuje tento atribut aplikovaný na vlastnost instance.

```vb
Imports System
Imports System.Diagnostics

Namespace Microsoft.Samples

    Public Class TestClass

        ' [...]

        <DebuggerBrowsable(DebuggerBrowsableState.Never)> _
        Public ReadOnly Property LargeObject() As LargeObject
            Get
                ' Allocate large object
                ' [...]
            End Get
        End Property

    End Class

End Namespace
```

```csharp
using System;
using System.Diagnostics;

namespace Microsoft.Samples
{
    publicclass TestClass
    {
        // [...]

        [DebuggerBrowsable(DebuggerBrowsableState.Never)]
        public LargeObject LargeObject
        {
            get
            {
                // Allocate large object
                // [...]
            }
        }
    }
}
```

## <a name="example"></a>Příklad

Následující příklad obsahuje několik metod, které by měly být převedeny na vlastnosti a několik, které by neměly být stejné, protože se chovají jako pole.

[!code-csharp[FxCop.Design.MethodsProperties#1](../code-quality/codesnippet/CSharp/ca1024-use-properties-where-appropriate_1.cs)]