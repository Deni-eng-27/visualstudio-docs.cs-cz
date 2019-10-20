---
title: Refaktoring kódu pro převod smyčky for na příkaz foreach
ms.date: 05/10/2018
ms.topic: reference
author: jillre
ms.author: jillfra
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- dotnet
ms.openlocfilehash: 3d35897bd928166410ffd950534277cfac2c06b7
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/19/2019
ms.locfileid: "72654544"
---
# <a name="refactoring-to-convert-between-a-for-loop-and-a-foreach-statement"></a>Refaktoring pro převod mezi smyčkou for a příkazem foreach

Tento článek popisuje refaktoring rychlých akcí, které převádějí mezi dvě struktury smyček. Obsahuje některé důvody, proč můžete chtít přepínat mezi smyčkou [for](/dotnet/csharp/language-reference/keywords/for) a příkazem [foreach](/dotnet/csharp/language-reference/keywords/foreach-in) v kódu.

## <a name="convert-a-for-loop-to-a-foreach-statement"></a>Převod smyčky for na příkaz foreach

Pokud máte ve svém kódu smyčku [for](/dotnet/csharp/language-reference/keywords/for) , můžete tento refaktoring použít k převedení na příkaz [foreach](/dotnet/csharp/language-reference/keywords/foreach-in) .

Tento refaktoring platí pro:

- C#

> [!NOTE]
> Refaktoring rychlé akce **převést na foreach** je k dispozici pouze [pro smyčky,](/dotnet/csharp/language-reference/keywords/for) které obsahují všechny tři části: inicializátor, podmínka a iterátor.

### <a name="why-convert"></a>Proč převést

Důvody, proč je vhodné převést smyčku [for](/dotnet/csharp/language-reference/keywords/for) na příkaz [foreach](/dotnet/csharp/language-reference/keywords/foreach-in) , zahrnují:

- V rámci smyčky nepoužíváte proměnnou lokální smyčky s výjimkou indexu pro přístup k položkám.

- Chcete zjednodušit svůj kód a snížit pravděpodobnost chyb logického prostředí v částech inicializátoru, podmínky a iterátoru.

### <a name="how-to-use-it"></a>Jak ji použít

1. Umístěte blikající kurzor do klíčového slova `for`.

1. Stiskněte klávesu **Ctrl** + **.** nebo klikněte na ikonu ![Screwdriver Screwdriver ](../media/screwdriver-icon.png) ikonu na okraji souboru s kódem.

   ![Nabídka převést na foreach](media/convert-to-foreach.png)

1. Vyberte **převést na foreach**. Případně můžete výběrem **Zobrazit náhled změn** otevřít dialogové okno [Náhled změn](../../ide/preview-changes.md) a pak vybrat **použít**.

## <a name="convert-a-foreach-statement-to-a-for-loop"></a>Převod příkazu foreach na smyčku for

Pokud máte příkaz [foreach (C#)](/dotnet/csharp/language-reference/keywords/foreach-in) nebo [for each... Následující (Visual Basic)](/dotnet/visual-basic/language-reference/statements/for-each-next-statement) příkaz v kódu, můžete použít tento refaktoring k převedení na smyčku [for](/dotnet/csharp/language-reference/keywords/for) .

Tento refaktoring platí pro:

- C#

- Visual Basic

### <a name="why-convert"></a>Proč převést

Důvody, které byste mohli chtít převést příkaz [foreach](/dotnet/csharp/language-reference/keywords/foreach-in) do smyčky [for](/dotnet/csharp/language-reference/keywords/for) , zahrnují:

- Chcete použít proměnnou lokální smyčky uvnitř smyčky pro více než jenom přístup k položce.

- Provádíte [iteraci](/dotnet/csharp/programming-guide/arrays/using-foreach-with-arrays) v multidimenzionálním poli a chcete mít větší kontrolu nad prvky pole.

### <a name="how-to-use-it"></a>Jak ji použít

1. Umístěte blikající kurzor do klíčového slova `foreach` nebo `For Each`.

1. Stiskněte klávesu **Ctrl** + **.** nebo klikněte na ikonu ![Screwdriver Screwdriver ](../media/screwdriver-icon.png) ikonu na okraji souboru s kódem.

   ![Nabídka převést na pro](media/convert-to-for.png)

1. Vyberte **převést na pro**. Případně můžete výběrem **Zobrazit náhled změn** otevřít dialogové okno [Náhled změn](../../ide/preview-changes.md) a pak vybrat **použít**.

1. Vzhledem k tomu, že refaktoring zavádí novou proměnnou počtu iterací, zobrazí se pole **Přejmenovat** v pravém horním rohu editoru. Chcete-li pro proměnnou zvolit jiný název, zadejte ji do pole a potom stiskněte klávesu **ENTER** nebo zvolte možnost **použít** v poli **Přejmenovat** . Pokud nechcete zvolit nový název, stiskněte klávesu **ESC** nebo vyberte **použít** k zavření pole **Přejmenovat** .

> [!NOTE]
> Pro C#kód, který vygenerovaly tyto refaktoringy, používá explicitní typ nebo [var](/dotnet/csharp/language-reference/keywords/var) pro typ položek v kolekci. Typ v generovaném kódu, explicitní nebo implicitní, závisí na nastavení stylu kódu, které jsou v rozsahu. Tato konkrétní nastavení stylu kódu se konfigurují na úrovni počítače v nabídce **nástroje**  > **Možnosti**  > **textový Editor** **C#**  >   > **styl kódu** 0**Obecné** 2 **@no__t_ 14var ' předvolby**nebo na úrovni řešení v souboru [EditorConfig](../../ide/editorconfig-language-conventions.md#implicit-and-explicit-types) . Pokud změníte nastavení stylu kódu v **možnostech**, znovu otevřete soubor kódu, aby se změny projevily.

## <a name="see-also"></a>Viz také:

- [Refactoring](../refactoring-in-visual-studio.md)
- [Náhled změn](../../ide/preview-changes.md)