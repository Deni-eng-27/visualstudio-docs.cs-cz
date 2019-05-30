---
title: Commandtable – Element | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- CommandTable
helpviewer_keywords:
- CommandTable element (VSCT XML schema)
- VSCT XML schema elements, CommandTable
ms.assetid: 15c38159-660a-4ef4-9643-aa6fcfca82a9
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 9bb10232c725eb2f538df73f6a7ca98e534a4c14
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66341810"
---
# <a name="commandtable-element"></a>Commandtable – element
Je kořenový element z commandtable – *.vsct* souboru. Toto je soubor, který definuje skutečný rozložení a typ příkazů, které poskytuje VSPackage pro prostředí IDE. Příkazy mohou být položky nabídky, nabídky, panely nástrojů a pole se seznamem. Další informace najdete v tématu [soubory tabulky (.vsct) příkazů sady Visual Studio](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md).

## <a name="syntax"></a>Syntaxe

```xml
<CommandTable xmlns="http://schemas.microsoft.com/VisualStudio/2005-10-18/CommandTable" xmlns:xs="http://www.w3.org/2001/XMLSchema" >
  <Extern>... </Extern>
  <Include>... </Include>
  <Define>... </Define>
  <Commands>... </Commands>
  <CommandPlacements>... </CommandPlacements>
  <VisibilityConstraints>... </VisibilityConstraints>
  <KeyBindings>... </KeyBindings>
  <UsedCommands... </UsedCommands>
  <Symbols>... </Symbols>
</CommandTable>
```

## <a name="attributes-and-elements"></a>Atributy a elementy
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.

### <a name="attributes"></a>Atributy

| Atribut | Popis |
|-----------| - |
| xmlns | Povinný parametr. Obory názvů XML:<br /><br /> xmlns="<http://schemas.microsoft.com/VisualStudio/2005-10-18/CommandTable>"<br /><br /> xmlns:xs="<http://www.w3.org/2001/XMLSchema>" |
| jazyk | Volitelné. Atribut language slouží k určení výchozí jazyk všech \<řetězce > prvků v tabulce příkazu.  Pokud jazyk není zadán, použije se jazyk aktuálního procesu:<br /><br /> jazyk = "en-us" |

### <a name="child-elements"></a>Podřízené elementy

|Prvek|Popis|
|-------------|-----------------|
|[Extern – element](../extensibility/extern-element.md)|Volitelné. Obsahuje direktivy preprocesoru kompilátoru jazyka.|
|[Prvek direktivy include](../extensibility/include-element.md)|Volitelné. Obsahuje cesty k souborům, které chcete zahrnout do kompilace.|
|[Define – element](../extensibility/define-element.md)|Volitelné. Definuje symbol zadanou její název a hodnotu.|
|[Commands – element](../extensibility/commands-element.md)|Volitelné. Definování všechny příkazy pro sady VSPackage, která obsahuje všechny ostatní prvky nadřazeného elementu.|
|[Commandplacements – element](../extensibility/commandplacements-element.md)|Volitelné. Definuje, kde na panelu příkazů příkazy mají být umístěny.|
|[Visibilityconstraints – element](../extensibility/visibilityconstraints-element.md)|Volitelné. Určuje statické viditelnost příkazů a panely nástrojů.|
|[Keybindings – element](../extensibility/keybindings-element.md)|Volitelné. Určuje kombinace klávesových zkratek, pokud existuje, pro příkazy.|
|[Usedcommands – element](../extensibility/usedcommands-element.md)|Volitelné. Umožňuje VSPackage volitelně implementovat svou vlastní verzi funkce původně podporuje další rozšíření VSPackages.|
|[Symbols – element](https://www.microsoft.com/download/details.aspx?id=55984)|Volitelné. Obsahuje všechna data symbol--identifikátory GUID, ID a tak dále--pro kompilátor.|

### <a name="parent-elements"></a>Nadřazené prvky

|Prvek|Popis|
|-------------|-----------------|
|Žádný||

## <a name="see-also"></a>Viz také:
- [Soubory tabulky (.vsct) příkaz pro Visual Studio](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)