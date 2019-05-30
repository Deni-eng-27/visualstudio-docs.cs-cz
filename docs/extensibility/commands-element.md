---
title: Příkazy Element | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- Commands
helpviewer_keywords:
- Commands element (VSCT XML schema)
- VSCT XML schema elements, Commands
ms.assetid: 47cf16a5-d78b-452e-86f6-b5893856dddf
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: ab8629fb3ef83277f1366a5141c400b8eeea70e3
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66341900"
---
# <a name="commands-element"></a>Commands – element
Představuje kolekci příkazů na panelu nástrojů VSPackage. Kolekce může mít až o pěti pododdíly následujícím způsobem: nabídek, skupiny, tlačítka, kláves a rastrových obrázků.

 Každý dílčí část podřízený prvek, například \<nabídky >, je identifikován jedinečný příkaz ID, které je identifikátor GUID a číselný identifikátor pár. Identifikátor GUID identifikuje sadu příkazů"" a slouží k seskupení logicky spojených příkazy. Sady VSPackage by měl definovat vlastní sadu pro zabránění kolizím s ID příkazů, které jsou definovány ostatní rozšíření VSPackages příkazů.

## <a name="syntax"></a>Syntaxe

```xml
<Commands package="GuidMyPackage" >
  <Menus>... </Menus>
  <Groups>... </Groups>
  <Buttons>... </Buttons>
  <Combos>... </Combos>
  <Bitmaps>... </Bitmaps>
</Commands>
```

## <a name="attributes-and-elements"></a>Atributy a elementy
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.

### <a name="attributes"></a>Atributy

|Atribut|Popis|
|---------------|-----------------|
|Balíček|Identifikátor GUID, který identifikuje sady VSPackage, která poskytuje příkazy.<br /><br /> Třeba balíček = "guidVsPackage1Pkg".|

### <a name="child-elements"></a>Podřízené prvky

|Prvek|Popis|
|-------------|-----------------|
|[Menus – element](../extensibility/menus-element.md)|Definuje všechny nabídky, které implementuje VSPackage.|
|[Groups – element](../extensibility/groups-element.md)|Obsahuje položky, které definují skupinu příkazů v sadě VSPackage.|
|[Buttons – element](../extensibility/buttons-element.md)|Seskupí elementy tlačítko.|
|[Bitmaps – element](../extensibility/bitmaps-element.md)|Seskupí elementy rastrového obrázku.|
|[Combos – element](../extensibility/combos-element.md)|Prvky pole se seznamem skupin.|

### <a name="parent-elements"></a>Nadřazené prvky

|Prvek|Popis|
|-------------|-----------------|
|[Commandtable – element](../extensibility/commandtable-element.md)|Definuje všechny prvky, které představují příkazy, které poskytuje VSPackage pro prostředí IDE. Je to možné prvky jsou položky nabídky, nabídky, panely nástrojů a pole se seznamem.|

## <a name="example"></a>Příklad
 Následující příklad ukazuje způsob použití [Commands – Element](../extensibility/commands-element.md).

```
<Commands package="guidMyPackage">
    <Menus>
      <Menu Condition="'%(DEBUG)' != 'true'"
        guid="cmdSetGuidMyProductCommands" id="menuIDMainMenu"
        priority="0x0000" type="Menu">
        <Annotation>
          <Documentation>this is an annotation</Documentation>
          <AppInfo>
            <CustomData>
              <CustomSubElement>Some data</CustomSubElement>
            </CustomData>
          </AppInfo>
        </Annotation>
        <CommandFlag>AlwaysCreate</CommandFlag>
        <Strings>
          <ButtonText>MainMenu</ButtonText>
        </Strings>
      </Menu>
  </Menus>
<Commands>
```

## <a name="see-also"></a>Viz také:
- [Jak balíčky VSPackages přidávají prvky uživatelského rozhraní](../extensibility/internals/how-vspackages-add-user-interface-elements.md)
- [Příkazy, nabídky a panely nástrojů](../extensibility/internals/commands-menus-and-toolbars.md)