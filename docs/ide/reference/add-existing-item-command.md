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
ms.openlocfilehash: d91e84a817b7b68f56c053d11d69facf753c6efc
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68919388"
---
# <a name="add-existing-item-command"></a>Přidat existující položku – příkaz
Přidá existující soubor do aktuálního řešení a otevře jej.

## <a name="syntax"></a>Syntaxe

```cmd
File.AddExistingItem filename [/e:editorname]
```

## <a name="arguments"></a>Arguments
`filename`\
Povinný parametr. Úplná cesta a název souboru s příponou položky, která se má přidat do aktuálního řešení. Pokud cesta nebo název souboru obsahují mezery, uzavřete celou cestu do uvozovek.

## <a name="switches"></a>Přepínače
/e`editorname`\
Volitelné. Název editoru, ve kterém bude soubor otevřen. Je-li zadán argument, ale není zadán žádný název editoru, zobrazí se dialogové okno **otevřít v** .

Syntaxe/e:`editorname` argument používá názvy editoru tak, jak se zobrazí v **dialogovém okně Otevřít v aplikaci**uzavřené v uvozovkách. Chcete-li například otevřít šablonu stylů v editoru zdrojového kódu, zadejte následující příkaz pro parametr/e:`editorname` .

```cmd
/e:"Source Code (text) Editor"
```

## <a name="remarks"></a>Poznámky
Automatické dokončování se snaží vyhledat správnou cestu a název souboru při psaní.

## <a name="example"></a>Příklad
Tento příklad přidá soubor. Form1. frm do aktuálního řešení.

```cmd
>File.AddExistingItem "C:\public\solution files\Form1.frm"
```

## <a name="see-also"></a>Viz také

- [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)
- [Příkazové okno](../../ide/reference/command-window.md)
- [Pole Najít/příkaz](../../ide/find-command-box.md)
- [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)