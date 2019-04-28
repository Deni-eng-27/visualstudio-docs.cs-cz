---
title: Visibilityconstraints – Element | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- VisibilityConstraints
helpviewer_keywords:
- VSCT XML schema elements, VisibilityConstraints
- VisibilityConstraints element (VSCT XML schema)
ms.assetid: d6dcd314-6fe4-4693-a189-91fa026c7b34
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: b5dfbeb3c45e05c93554aae9b17a42c265408bc3
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62839033"
---
# <a name="visibilityconstraints-element"></a>Visibilityconstraints – element
Visibilityconstraints – element určuje statické viditelnost skupiny příkazů a panely nástrojů. Nejprve řídí viditelnost [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] integrované vývojové prostředí (IDE) bez načtení sady VSPackage.

## <a name="syntax"></a>Syntaxe

```xml
<VisibilityConstraints>
  <VisibilityItem />
  <VisibilityItem />
</VisibilityConstraints>
```

## <a name="attributes-and-elements"></a>Atributy a elementy
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.

### <a name="attributes"></a>Atributy

|Atribut|Popis|
|---------------|-----------------|
|Podmínka|Volitelné. Zobrazit [podmíněné atributy](../extensibility/vsct-xml-schema-conditional-attributes.md).|

### <a name="child-elements"></a>Podřízené prvky

|Prvek|Popis|
|-------------|-----------------|
|[Visibilityitem – element](../extensibility/visibilityitem-element.md)|Určuje statické viditelnost příkazů a panely nástrojů.|
|[Visibilityconstraints –](../extensibility/visibilityconstraints-element.md)|Určuje, zda statických skupin příkazů a panely nástrojů.|

### <a name="parent-elements"></a>Nadřazené prvky

|Prvek|Popis|
|-------------|-----------------|
|[Commandtable – element](../extensibility/commandtable-element.md)|Definuje všechny prvky, které představují příkazy (například položek nabídky, nabídky, panely nástrojů a pole se seznamem), které poskytuje VSPackage pro prostředí IDE.|

## <a name="example"></a>Příklad

```xml
<VisibilityConstraints>
  <VisibilityItem guid="cmdSetGuidMyProductCommands"     id="cmdidAddWidget"
    context="guidNotViewSourceMode"/>
</VisibilityConstraints>
```

## <a name="see-also"></a>Viz také:
- [Visibilityitem – element](../extensibility/visibilityitem-element.md)
- [Visual Studio tabulky příkazů (. Soubory Vsct)](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)
