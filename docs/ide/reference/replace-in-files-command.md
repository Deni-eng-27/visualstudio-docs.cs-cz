---
title: Nahradit v souborech – příkaz
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- edit.replaceinfiles
helpviewer_keywords:
- Edit.ReplaceInFiles command
- Replace In Files command
- ReplaceInFiles command
ms.assetid: f116066a-4f65-4f2c-94ef-12cbd8cfb598
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: fccfe696da2d38ff03ffb2f9b91de481e924a514
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/22/2019
ms.locfileid: "72748670"
---
# <a name="replace-in-files-command"></a>Nahradit v souborech – příkaz
Nahradí text v souborech pomocí podmnožiny možností, které jsou k dispozici na kartě **nahradit v souborech** okna **Najít a nahradit** .

## <a name="syntax"></a>Syntaxe

```
Edit.ReplaceinFiles findwhat replacewith [/all] [/case]
[/ext:extensions] [/keep] [/lookin:searchpath] [/options] [/regex]
[/reset] [/stop] [/sub] [/text2] [/wild] [/word]
```

## <a name="arguments"></a>Arguments
`findwhat`

Požadováno. Text, který se má shodovat.

`replacewith`

Požadováno. Text, který má být nahrazen odpovídajícím textem

## <a name="switches"></a>Přepínače
/All nebo/a

Volitelné. Nahradí všechny výskyty hledaného textu náhradním textem.

/Case nebo/c

Volitelné. Shody se objeví pouze v případě, že se velká a malá písmena přesně shodují s hodnotami zadanými v argumentu `findwhat`.

/EXT: `extensions`

Volitelné. Určuje přípony souborů pro soubory, které mají být prohledány.

/Keep nebo/k

Volitelné. Určuje, že všechny změněné soubory zůstanou otevřené.

/Lookin: `searchpath`

Volitelné. Adresář, který chcete vyhledat. Pokud cesta obsahuje mezery, uzavřete celou cestu do uvozovek.

/Options nebo/t

Volitelné. Zobrazí seznam aktuálních nastavení možností hledání a neprovádí hledání.

/Regex nebo/r

Volitelné. Používá předem definované speciální znaky v argumentu `findwhat` jako notace, které reprezentují vzory textu, nikoli literální znaky. Úplný seznam znaků regulárních výrazů naleznete v tématu [regulární výrazy](../../ide/using-regular-expressions-in-visual-studio.md).

/Reset po vyčištění nebo/e

Volitelné. Vrátí možnosti hledání do jejich výchozího nastavení a neprovádí hledání.

/stop

Volitelné. Zastaví aktuální operaci hledání, pokud právě probíhá. Při zadání `/stop` parametr nahradit ignoruje všechny ostatní argumenty. Pokud například chcete zastavit aktuální nahrazení, zadejte následující:

```
>Edit.ReplaceinFiles /stop
```

/Sub nebo/s

Volitelné. Vyhledá podsložky v adresáři zadaném v argumentu/Lookin: `searchpath`.

/Text2 nebo/2

Volitelné. Zobrazí výsledky náhrady v okně **výsledky hledání 2** .

/Wild nebo/l

Volitelné. Používá předem definované speciální znaky v argumentu `findwhat` jako notace, které reprezentují znak nebo sekvenci znaků.

/Word nebo/w

Volitelné. Vyhledá pouze celá slova.

## <a name="example"></a>Příklad
Tento příklad vyhledá `btnCancel` a nahradí jej `btnReset` ve všech souborech. CLS umístěných ve složce "Moje projekty sady Visual Studio" a zobrazí informace o nahrazení v okně **výsledky hledání 2** .

```
>Edit.ReplaceinFiles btnCancel btnReset /lookin:"c:/my visual studio projects" /ext:.cls /text2
```

## <a name="see-also"></a>Viz také:

- [Hledání a nahrazení textu](../../ide/finding-and-replacing-text.md)
- [Nahradit v souborech](../../ide/replace-in-files.md)
- [Příkazové okno](../../ide/reference/command-window.md)
- [Pole Najít/příkaz](../../ide/find-command-box.md)
- [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)
- [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)