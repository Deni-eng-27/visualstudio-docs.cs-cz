---
title: Přidat existující projekt – příkaz
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- file.addexistingproject
helpviewer_keywords:
- Add Existing Project command
- File.AddExistingProject
ms.assetid: 71cf3e31-c76b-405b-ad6a-1b1bc654bd40
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 008802546d87bd44137c6d13ee2aef802877e308
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "75595875"
---
# <a name="add-existing-project-command"></a>Přidat existující projekt – příkaz
Přidá existující projekt k aktuálnímu řešení.

## <a name="syntax"></a>Syntaxe

```cmd
File.AddExistingProject filename
```

## <a name="arguments"></a>Argumenty
`filename`\
Nepovinný parametr. Úplná cesta a název projektu s příponou projektu, který se má přidat do řešení.

Pokud `filename` argument obsahuje mezery, musí být uzavřen v uvozovkách.

Pokud není zadán žádný název souboru, příkaz otevře dialogové okno souboru, aby mohl uživatel vybrat projekt.

## <a name="remarks"></a>Poznámky
Automatické dokončování se snaží vyhledat správnou cestu a název souboru při psaní.

## <a name="example"></a>Příklad
Tento příklad přidá [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] projekt TestProject1 do aktuálního řešení.

```cmd
>File.AddExistingProject "c:\visual studio projects\TestProject1.vbproj"
```

## <a name="see-also"></a>Viz také

- [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)
- [Příkazové okno](../../ide/reference/command-window.md)
- [Pole Najít/příkaz](../../ide/find-command-box.md)
- [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)
