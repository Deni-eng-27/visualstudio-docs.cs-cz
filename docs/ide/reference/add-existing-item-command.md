---
title: Přidat existující položku – příkaz
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- project.addexistingitem
helpviewer_keywords:
- File.AddExistingItem command
- Add Existing Item command
ms.assetid: 41f56131-d4c7-4f81-83b7-bdac713ea870
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b8ab2ce6e9f1260172bf0ffbf0aede9138a5115f
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62792620"
---
# <a name="add-existing-item-command"></a>Přidat existující položku – příkaz
Přidá existující soubor do aktuálního řešení a otevře jej.

## <a name="syntax"></a>Syntaxe

```cmd
File.AddExistingItem filename [/e:editorname]
```

## <a name="arguments"></a>Arguments
 `filename` Povinné. Úplná cesta a název souboru, s rozšířením položky pro přidání do aktuálního řešení. Pokud cesta k souboru nebo název souboru obsahuje mezery, uzavřete do uvozovek celou cestu.

## <a name="switches"></a>Přepínače
 /e: `editorname` Volitelné. Název editoru, ve kterém chcete soubor otevřít. Pokud je zadán argument, ale žádný editor název je zadán, **otevřít v** zobrazí se dialogové okno.

 / E:`editorname` syntaxí argumentů používá názvy editoru, jak se objeví v **otevřít s dialogové okno**, uzavřené v uvozovkách. Chcete-li otevřít šablony stylů v editoru zdrojového kódu, by například zadejte následující pro / e:`editorname` argument.

```cmd
/e:"Source Code (text) Editor"
```

## <a name="remarks"></a>Poznámky
 Automatického doplňování pokusí se najít správnou cestu a název souboru během psaní.

## <a name="example"></a>Příklad
 Tento příklad přidá soubor Form1.frm, do aktuálního řešení.

```cmd
>File.AddExistingItem "C:\public\solution files\Form1.frm"
```

## <a name="see-also"></a>Viz také

- [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)
- [Příkazové okno](../../ide/reference/command-window.md)
- [Pole Najít/příkaz](../../ide/find-command-box.md)
- [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)