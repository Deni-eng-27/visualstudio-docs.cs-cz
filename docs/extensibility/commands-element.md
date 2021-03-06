---
title: Command – element | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- Commands
helpviewer_keywords:
- Commands element (VSCT XML schema)
- VSCT XML schema elements, Commands
ms.assetid: 47cf16a5-d78b-452e-86f6-b5893856dddf
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 3ea2400cca19a02475caecec3d022e0b78794ae4
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "80739684"
---
# <a name="commands-element"></a>Command – element
Představuje kolekci příkazů na panelu nástrojů VSPackage. Kolekce může obsahovat až pět dílčích částí, a to takto: nabídky, skupiny, tlačítka, Combos a bitmapy.

 Každý podřízený element dílčího oddílu, například \<Menu> , je identifikován jedinečným identifikátorem příkazu, který je identifikátor GUID a dvojice čísel identifikátorů. Identifikátor GUID identifikuje "sadu příkazů" a používá se k seskupení příkazů souvisejících s logicky. VSPackage by měl definovat svou vlastní sadu příkazů, aby se předešlo kolizím s identifikátory příkazů, které jsou definovány jinými rozhraními VSPackage.

## <a name="syntax"></a>Syntax

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
|balíček|Identifikátor GUID, který identifikuje VSPackage, který poskytuje příkazy.<br /><br /> Například Package = "guidVsPackage1Pkg".|

### <a name="child-elements"></a>Podřízené prvky

|Element|Popis|
|-------------|-----------------|
|[Menu – element](../extensibility/menus-element.md)|Definuje všechny nabídky, které implementuje VSPackage.|
|[Groups – element](../extensibility/groups-element.md)|Obsahuje položky, které definují skupiny příkazů ve VSPackage.|
|[Buttons – Element](../extensibility/buttons-element.md)|Prvky tlačítka skupiny|
|[Rastrové obrázky – element](../extensibility/bitmaps-element.md)|Seskupuje rastrové prvky.|
|[Element Combos](../extensibility/combos-element.md)|Seskupuje prvky se seznamem.|

### <a name="parent-elements"></a>Nadřazené prvky

|Element|Popis|
|-------------|-----------------|
|[Element v příkazu](../extensibility/commandtable-element.md)|Definuje všechny prvky, které představují příkazy, které VSPackage poskytuje rozhraní IDE. Možné elementy jsou položky nabídky, nabídky, panely nástrojů a pole se seznamem.|

## <a name="example"></a>Příklad
 Následující příklad ukazuje, jak použít [element Commands](../extensibility/commands-element.md).

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

## <a name="see-also"></a>Viz také
- [Jak prvky VSPackage přidávají prvky uživatelského rozhraní](../extensibility/internals/how-vspackages-add-user-interface-elements.md)
- [Příkazy, nabídky a panely nástrojů](../extensibility/internals/commands-menus-and-toolbars.md)
