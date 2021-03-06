---
title: Ladit. tisk
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- debug.print
helpviewer_keywords:
- Debug.Print command
- Print method
- Print command
ms.assetid: 0412d381-590a-483f-bab4-6e1cca095645
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 3056570e52893f1c21eaf10c7856b21fbbc02c61
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "75567837"
---
# <a name="print-command"></a>Tisk – příkaz

Vyhodnotí výraz nebo zobrazí zadaný text.

## <a name="syntax"></a>Syntaxe

```cmd
>Debug.Print text
```

## <a name="arguments"></a>Argumenty

`text`

Povinná hodnota. Výraz, který se má vyhodnotit, nebo text, který se má zobrazit

## <a name="remarks"></a>Poznámky

Jako alias pro tento příkaz můžete použít otazník (?). Například příkaz

```cmd
>Debug.Print expA
```

lze také zapsat jako

```cmd
? expA
```

Obě verze tohoto příkazu vracejí aktuální hodnotu výrazu `expA` .

## <a name="example"></a>Příklad

```cmd
>Debug.Print DateTime.Now.Day
```

## <a name="see-also"></a>Viz také

- [Evaluate – příkaz příkazu](../../ide/reference/evaluate-statement-command.md)
- [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)
- [Příkazové okno](../../ide/reference/command-window.md)
- [Pole Najít/příkaz](../../ide/find-command-box.md)
- [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)
