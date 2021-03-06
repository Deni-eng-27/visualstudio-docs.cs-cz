---
title: Přidat novou položku – příkaz
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- project.addnewitem
helpviewer_keywords:
- Add New Item command
- File.AddNewItem command
ms.assetid: 63b7df32-db83-463b-bbe7-7ff011fe5298
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 38be691ae7c49ffbd6c98c9e4beb25b6ebb021b6
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "75585688"
---
# <a name="add-new-item-command"></a>Přidat novou položku – příkaz
Přidá novou položku řešení, jako je například. htm,. CSS,. txt nebo FRAMESET, do aktuálního řešení a otevře se.

## <a name="syntax"></a>Syntaxe

```cmd
File.AddNewItem [filename] [/t:templatename] [/e:editorname]
```

## <a name="arguments"></a>Argumenty
`filename`\
Nepovinný parametr. Cesta a název souboru položky, která se má přidat do řešení

## <a name="switches"></a>Přepínače
parametr `templatename`\
Nepovinný parametr. Určuje typ souboru, který se má vytvořit. Pokud není zadán žádný název šablony, je ve výchozím nastavení vytvořen textový soubor.

Syntaxe/t: `templatename` argument odráží informace, které se nacházejí v dialogovém okně **Přidat novou položku řešení** . Je nutné zadat celou kategorii, za kterou následuje typ souboru, oddělení názvu kategorie od typu souboru zpětným lomítkem ( `\` ) a uzavřením celého řetězce v uvozovkách.

Pokud například chcete vytvořit nový textový soubor, zadejte do argumentu/t: následující text `templatename` .

```cmd
/t:"General\Style Sheet"
```

/e `editorname`\
Nepovinný parametr. Název editoru, ve kterém bude soubor otevřen. Je-li zadán argument, ale není zadán žádný název editoru, zobrazí se dialogové okno **otevřít v** .

Syntaxe/e: `editorname` argument používá názvy editoru tak, jak se zobrazí v **dialogovém okně Otevřít v aplikaci**uzavřené v uvozovkách.

Chcete-li například otevřít šablonu stylů v editoru zdrojového kódu, zadejte následující příkaz pro parametr/e: `editorname` .

```cmd
/e:"Source Code (text) Editor"
```

## <a name="example"></a>Příklad
Tento příklad přidá novou položku řešení MyHTMLpg do aktuálního řešení.

```cmd
>File.AddNewItem MyHTMLpg /t:"General\HTML Page"
```

## <a name="see-also"></a>Viz také

- [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)
- [Příkazové okno](../../ide/reference/command-window.md)
- [Pole Najít/příkaz](../../ide/find-command-box.md)
- [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)
