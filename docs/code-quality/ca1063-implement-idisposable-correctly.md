---
title: 'CA1063: Implementuje správně IDisposable'
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- ImplementIDisposableCorrectly
- CA1063
helpviewer_keywords:
- CA1063
- ImplementIDisposableCorrectly
ms.assetid: 12afb1ea-3a17-4a3f-a1f0-fcdb853e2359
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- multiple
ms.openlocfilehash: 837659ca24eb66995626668185500db7bc32bbd7
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/16/2019
ms.locfileid: "69547370"
---
# <a name="ca1063-implement-idisposable-correctly"></a>CA1063: Implementuje správně IDisposable

|||
|-|-|
|TypeName|ImplementIDisposableCorrectly|
|CheckId|CA1063|
|Kategorie|Microsoft.Design|
|Narušující změna|Nenarušující|

## <a name="cause"></a>příčina

<xref:System.IDisposable?displayProperty=nameWithType> Rozhraní není správně implementované. Mezi možné příčiny patří:

- <xref:System.IDisposable>je znovu implementován ve třídě.

- `Finalize`je znovu přepsán.

- `Dispose()`je přepsáno.

- Metoda není veřejná, zapečetěná nebo pojmenovaná **Dispose**. [](/dotnet/csharp/language-reference/keywords/sealed) `Dispose()`

- `Dispose(bool)`není chráněný, virtuální ani nezapečetěný.

- V nezapečetěných typech `Dispose()` musí volat `Dispose(true)`.

- Pro nezapečetěné typy `Finalize` implementace nevolá buď `Dispose(bool)` ani, nebo finalizační metodu základní třídy.

Porušení některého z těchto vzorů vyvolá upozornění CA1063.

Každý nezapečetěný typ, který deklaruje a implementuje <xref:System.IDisposable> rozhraní, musí poskytovat svou vlastní `protected virtual void Dispose(bool)` metodu. `Dispose()`by měl `Dispose(true)`zavolat a finalizační metoda by měla volat `Dispose(false)`. Pokud vytvoříte nezapečetěný typ, který deklaruje a implementuje <xref:System.IDisposable> rozhraní, je nutné jej definovat `Dispose(bool)` a volat. Další informace najdete v tématu [Vymazání nespravovaných prostředků (Průvodce .NET)](/dotnet/standard/garbage-collection/unmanaged) a [vzor Dispose](/dotnet/standard/design-guidelines/dispose-pattern).

Ve výchozím nastavení toto pravidlo vyhledává pouze externě viditelné typy, ale je možné jej [nakonfigurovat](#configurability).

## <a name="rule-description"></a>Popis pravidla

Všechny <xref:System.IDisposable> typy by měly implementovat správně [vzor Dispose](/dotnet/standard/design-guidelines/dispose-pattern) .

## <a name="how-to-fix-violations"></a>Jak opravit porušení

Zkontrolujte svůj kód a určete, která z následujících řešení vyřeší toto porušení:

- Odeberte <xref:System.IDisposable> ze seznamu rozhraní implementovaných vaším typem a místo toho přepište implementaci Dispose základní třídy.

- Odeberte finalizační metodu z vašeho typu, přepište Dispose (bool disposing) a vložte logiku finalizace do cesty kódu, kde ' disposing ' má hodnotu false.

- Přepište Dispose (bool disposing) a vložte logiku Dispose do cesty kódu, kde má vlastnost ' disposing ' hodnotu true.

- Ujistěte se, že metoda Dispose () je deklarována jako veřejná a [zapečetěná](/dotnet/csharp/language-reference/keywords/sealed).

- Přejmenujte metodu Dispose k **Dispose** a ujistěte se, že je deklarována jako veřejná a [zapečetěná](/dotnet/csharp/language-reference/keywords/sealed).

- Ujistěte se, že metoda Dispose (bool) je deklarována jako chráněná, virtuální a nezapečetěná.

- Upravte Dispose () tak, že volá Dispose (true), <xref:System.GC.SuppressFinalize%2A> potom volá aktuální instanci objektu (`this`nebo `Me` v Visual Basic) a pak se vrátí.

- Upravte finalizační metodu tak, že volá Dispose (false) a potom se vrátí.

- Pokud vytvoříte nezapečetěný typ, který deklaruje a implementuje <xref:System.IDisposable> rozhraní, ujistěte se, že <xref:System.IDisposable> implementace řídí následující vzor, který je popsán výše v této části.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Nepotlačujte upozornění na toto pravidlo.

## <a name="configurability"></a>Konfigurovatelnost

Pokud toto pravidlo spouštíte z [analyzátorů FxCop](install-fxcop-analyzers.md) (a ne pomocí starší verze analýzy), můžete nakonfigurovat, které části základu kódu mají spustit toto pravidlo, na základě jejich přístupnosti. Například chcete-li určit, že pravidlo by mělo běžet pouze proti neveřejnému povrchu rozhraní API, přidejte do souboru. editorconfig v projektu následující dvojici klíč-hodnota:

```ini
dotnet_code_quality.ca1063.api_surface = private, internal
```

Tuto možnost můžete nakonfigurovat jenom pro toto pravidlo, pro všechna pravidla nebo pro všechna pravidla v této kategorii (návrh). Další informace najdete v tématu [Konfigurace analyzátorů FxCop](configure-fxcop-analyzers.md).

## <a name="pseudo-code-example"></a>Příklad kódu pseudo-code

Následující pseudo kód poskytuje obecný příklad, jak Dispose (bool) by měla být implementována ve třídě, která používá spravované a nativní prostředky.

```csharp
public class Resource : IDisposable
{
    private IntPtr nativeResource = Marshal.AllocHGlobal(100);
    private AnotherResource managedResource = new AnotherResource();

    // Dispose() calls Dispose(true)
    public void Dispose()
    {
        Dispose(true);
        GC.SuppressFinalize(this);
    }

    // NOTE: Leave out the finalizer altogether if this class doesn't
    // own unmanaged resources, but leave the other methods
    // exactly as they are.
    ~Resource()
    {
        // Finalizer calls Dispose(false)
        Dispose(false);
    }

    // The bulk of the clean-up code is implemented in Dispose(bool)
    protected virtual void Dispose(bool disposing)
    {
        if (disposing)
        {
            // free managed resources
            if (managedResource != null)
            {
                managedResource.Dispose();
                managedResource = null;
            }
        }
        // free native resources if there are any.
        if (nativeResource != IntPtr.Zero)
        {
            Marshal.FreeHGlobal(nativeResource);
            nativeResource = IntPtr.Zero;
        }
    }
}
```

## <a name="see-also"></a>Viz také:

- [Vzor Dispose (pokyny pro návrh rozhraní)](/dotnet/standard/design-guidelines/dispose-pattern)
- [Vyčištění nespravovaných prostředků (Průvodce .NET)](/dotnet/standard/garbage-collection/unmanaged)