---
title: Visual Basic IntelliSense | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- IntelliSense [Visual Basic]
- IntelliSense [Visual Studio], Visual Basic
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 44ff32ed0452efb5e413d730a69293147fec4c7c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="intellisense-for-visual-basic-code-files"></a>IntelliSense pro soubory s kódem jazyka Visual Basic

Editor kódu jazyka Visual Basic zdroj nabízí následující funkce IntelliSense:

## <a name="syntax-tips"></a>Syntaxe tipy

Syntaxe tipy zobrazení syntaxe příkazu, který zadáte. To je užitečné pro příkazy, jako například [Declare](/dotnet/visual-basic/language-reference/statements/declare-statement).

## <a name="automatic-completion"></a>Automatické dokončování

- Dokončení na různých klíčová slova

     Pokud zadáte například `goto` a místa, IntelliSense zobrazí seznam definovaných popisky v rozevírací nabídce. Zahrnout další podporované klíčová slova `Exit`, `Implements`, `Option`, a `Declare`.

- Dokončení na `Enum` a `Boolean`

    Pokud příkaz bude odkaz na člena výčtu, IntelliSense zobrazí seznam členů `Enum`. V případě bude příkaz odkazujete `Boolean`, IntelliSense zobrazí rozevírací nabídky hodnotu true na false.

Dokončení může být vypnuto ve výchozím nastavení pomocí zrušením výběru **automatický seznam členů** z **Obecné** stránka vlastností v **jazyka Visual Basic** složky.

Dokončení můžete vyvolat ručně vyvoláním vypsat členy, dokončení slovo nebo ALT + Šipka vpravo. Další informace najdete v tématu [pomocí IntelliSense](../ide/using-intellisense.md).

## <a name="intellisense-in-zone"></a>IntelliSense v zóně

IntelliSense v zóně pomáhá jazyka Visual Basic vývojáře, kteří potřebují nasazovat aplikace pomocí [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] a jsou omezená na nastavení částečné důvěryhodnosti. Tato funkce:

- Umožní vám vybrat oprávnění, která bude aplikace spuštěna s.

- Rozhraní API pro zobrazení v zvolený zónu jako dostupné v seznamu členů a zobrazit rozhraní API, které vyžadují další oprávnění jako nedostupné.

Další informace najdete v tématu [zabezpečení přístupu kódu pro aplikace ClickOnce](../deployment/code-access-security-for-clickonce-applications.md).

## <a name="filtered-completion-lists"></a>Filtrované seznamy dokončení

Seznamy dokončení IntelliSense v jazyce Visual Basic mít dva ovládací prvky karet umístěné v dolní části seznamy. **Běžné** kartu, která je standardně vybraná, zobrazí položky, které se nejčastěji používají k dokončení příkazu, který vytváříte. **Všechny** zobrazí všechny položky, které jsou k dispozici pro automatické dokončování, včetně těch, které jsou k dispozici také na kartě **běžné** kartě.

## <a name="see-also"></a>Viz také

[Používání atributu IntelliSense](../ide/using-intellisense.md)