---
title: Visual Basic IntelliSense
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.Basic.IntelliSense
helpviewer_keywords:
- IntelliSense [Visual Basic]
- IntelliSense [Visual Studio], Visual Basic
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 118de9ec05bcd5c56376376619bea0c5148d36ab
ms.sourcegitcommit: d233ca00ad45e50cf62cca0d0b95dc69f0a87ad6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/01/2020
ms.locfileid: "75594185"
---
# <a name="intellisense-for-visual-basic-code-files"></a>IntelliSense pro Visual Basic soubory kódu

Visual Basic Editor zdrojového kódu nabízí následující funkce technologie IntelliSense:

## <a name="syntax-tips"></a>Syntaxe tipy

V popisech syntaxe se zobrazuje syntaxe příkazu, který píšete. To je užitečné pro příkazy, jako je například [Declare](/dotnet/visual-basic/language-reference/statements/declare-statement).

## <a name="automatic-completion"></a>Automatické dokončování

- Dokončení u různých klíčových slov

     Například pokud zadáte `goto` a mezeru, IntelliSense zobrazí v rozevírací nabídce seznam definovaných popisků. Mezi další podporovaná klíčová slova patří `Exit`, `Implements`, `Option`a `Declare`.

- Dokončení při `Enum` a `Boolean`

    Pokud příkaz bude odkazovat na člen výčtu, technologie IntelliSense zobrazí seznam členů `Enum`. Když příkaz bude odkazovat na `Boolean`, IntelliSense zobrazí rozevírací nabídku true-false.

Dokončení může být vypnuto ve výchozím nastavení tím, že se na stránce **Obecné** vlastnosti ve složce **Visual Basic** odhlásí **Automatické seznam členů** .

Doplňování můžete ručně vyvolat vyvoláním členů seznamu, kompletního slova nebo **alternativního**+**šipky vpravo**. Další informace najdete v tématu [použití IntelliSense](../ide/using-intellisense.md).

## <a name="intellisense-in-zone"></a>IntelliSense v zóně

Technologie IntelliSense v zóně pomáhá Visual Basic vývojářům, kteří potřebují nasazovat aplikace přes [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] a jsou omezené na nastavení částečné důvěryhodnosti. Tato funkce:

- Umožňuje zvolit oprávnění, se kterými bude aplikace běžet.

- Zobrazit rozhraní API ve zvolené zóně jako dostupné v seznamech členů a zobrazit rozhraní API, která vyžadují další oprávnění jako nedostupná.

Další informace najdete v tématu [zabezpečení přístupu kódu pro aplikace ClickOnce](../deployment/code-access-security-for-clickonce-applications.md).

## <a name="filtered-completion-lists"></a>Filtrované seznamy dokončení

V Visual Basic mají seznamy pro dokončování IntelliSense dva ovládací prvky na kartě umístěné v dolní části seznamů. Karta **Common** , která je vybrána ve výchozím nastavení, zobrazuje položky, které jsou nejčastěji použity k dokončení příkazu, který píšete. Karta **vše** zobrazuje všechny položky, které jsou k dispozici pro automatické dokončování, včetně těch, které jsou také na kartě **Common** .

## <a name="see-also"></a>Viz také:

- [Používání technologie IntelliSense](../ide/using-intellisense.md)
