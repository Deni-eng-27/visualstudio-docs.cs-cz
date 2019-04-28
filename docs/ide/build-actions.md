---
title: Akce pro soubory sestavení
ms.date: 11/19/2018
ms.technology: vs-ide-compile
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 7820cbbe0477000c2a822e94f5204906d65025fa
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62975648"
---
# <a name="build-actions"></a>Akce sestavení

Všechny soubory v projektu Visual Studia mají akci sestavení. Proces sestavení určuje, co se stane soubor, když je projekt kompilován.

> [!NOTE]
> Toto téma se vztahuje k sadě Visual Studio ve Windows. Visual Studio pro Mac, najdete v části [akce v sadě Visual Studio pro Mac sestavení](/visualstudio/mac/build-actions).

## <a name="set-a-build-action"></a>Nastavte akci sestavení

Pokud chcete nastavit akci sestavení pro soubor, otevřete vlastnosti souboru v **vlastnosti** okna tak, že vyberete soubor v **Průzkumníka řešení** a stisknutím klávesy **Alt** + **Zadejte**. Nebo klikněte pravým tlačítkem na soubor v **Průzkumníka řešení** a zvolte **vlastnosti**. V **vlastnosti** okně v části **Upřesnit** části, pomocí rozevíracího seznamu vedle možnosti **akce sestavení** nastavit akci sestavení k souboru.

![Vytvoření akcí pro soubor v sadě Visual Studio](media/build-actions.png)

## <a name="build-action-values"></a>Akce hodnotách z buildu

Některé akce sestavení pro C# a soubory projektu Visual Basic jsou:

* **Žádný** – soubor není součástí sestavení žádným způsobem. Tuto hodnotu je možné pro soubory dokumentace, jako je například "Soubor ReadMe" soubory, např.
* **Kompilace** – soubor je předán kompilátoru jako zdrojový soubor.
* **Obsahu** – soubor označení **obsahu** dá načíst jako datový proud voláním <xref:System.Windows.Application.GetContentStream%2A?displayProperty=nameWithType>. Pro projekty ASP.NET tyto soubory jsou zahrnuty jako součást lokality při nasazení.
* **Vložený zdroj** – soubor je předán kompilátoru jako prostředek má být vložen do sestavení. Můžete volat <xref:System.Reflection.Assembly.GetManifestResourceStream%2A?displayProperty=fullName> přečíst soubor ze sestavení.
* **AdditionalFiles** -jinými než zdrojovými textový soubor, který je předán C# nebo kompilátor jazyka Visual Basic jako vstup. Tato akce sestavení se používá hlavně zadejte vstupy pro [analyzátory](../code-quality/roslyn-analyzers-overview.md) , který se odkazuje projekt k ověření kvality kódu. Další informace najdete v tématu [použít další soubory](https://github.com/dotnet/roslyn/blob/master/docs/analyzers/Using%20Additional%20Files.md).

## <a name="see-also"></a>Viz také:

- [Možnosti kompilátoru jazyka C#](/dotnet/csharp/language-reference/compiler-options/listed-alphabetically)
- [Možnosti kompilátoru jazyka Visual Basic](/dotnet/visual-basic/reference/command-line-compiler/compiler-options-listed-alphabetically)
- [Vytvoření akce (Visual Studio for Mac)](/visualstudio/mac/build-actions)