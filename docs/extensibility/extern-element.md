---
title: Extern – element | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- Extern
helpviewer_keywords:
- VSCT XML schema elements, Extern
- Extern element (VSCT XML schema)
ms.assetid: db6c3ddd-a1ba-450a-897a-bb568a5377fc
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 2cf6f9db77abaa7034af8d074b9833a4c1560f07
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "80711489"
---
# <a name="extern-element"></a>Extern – element
Element extern odkazuje na všechny soubory externích hlaviček (*. h*), které se mají sloučit se souborem *. vsct* v době kompilace. Soubory, které mají být sloučeny, musí být v cestě include zadané kompilátoru VSCT nebo odkazované [elementem include](../extensibility/include-element.md). Soubory mohou být jiné soubory *. vsct* nebo soubory hlaviček jazyka C++.

 Definice v hlavičkových souborech musí mít formát "#define [symbol] [hodnota]" hodnota může být jiný symbol, pokud je dříve definovaný. Definice mohou být použity v podmíněných příkazech položek příkazů. Libovolný symbol, který se ve skutečnosti nepoužívá, se zahodí.

 Element příkazu extern – element

## <a name="syntax"></a>Syntax

```xml
<Extern href="stdidcmd.h" />
```

## <a name="attributes-and-elements"></a>Atributy a elementy
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.

### <a name="attributes"></a>Atributy

|Atribut|Popis|
|---------------|-----------------|
|odkaz|Povinná hodnota. Cesta k souboru hlaviček:<br /><br /> href = "Stdidcmd. h"|
|Stav|Nepovinný parametr. Zobrazit [podmíněné atributy](../extensibility/vsct-xml-schema-conditional-attributes.md).|
|language|Nepovinný parametr. Výchozí jazyk všech [\<Strings>](../extensibility/strings-element.md) prvků v tabulce příkazů:<br /><br /> Language = "en-US"|

### <a name="child-elements"></a>Podřízené prvky

|Element|Popis|
|-------------|-----------------|
|Žádné|Žádné|

### <a name="parent-elements"></a>Nadřazené prvky

|Element|Popis|
|-------------|-----------------|
|[Element v příkazu](../extensibility/commandtable-element.md)|Definuje všechny prvky, které reprezentují příkazy, tj. položky nabídky, nabídky, panely nástrojů a pole se seznamem – to, že rozhraní VSPackage poskytuje integrované vývojové prostředí (IDE).|

## <a name="example"></a>Příklad

```xml
<?xml version="1.0" encoding="utf-8"?>
<CommandTable xmlns="http://schemas.microsoft.com/VisualStudio/2005-10-
  18/CommandTable" xmlns:xs="http://www.w3.org/2001/XMLSchema">
    <Extern href="C:\VSCore\vscommon\inc\vsshlids.h"/>
    ...
  <Commands package="guidMyPackage">
</CommandTable>
```

## <a name="see-also"></a>Viz také
- [Soubory tabulek příkazů sady Visual Studio (. vsct)](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)
- [Jak prvky VSPackage přidávají prvky uživatelského rozhraní](../extensibility/internals/how-vspackages-add-user-interface-elements.md)
- [Příkazy, nabídky a panely nástrojů](../extensibility/internals/commands-menus-and-toolbars.md)
