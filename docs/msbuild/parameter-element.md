---
title: Element parametru | Microsoft Docs
description: Přečtěte si o prvku parametru MSBuild, který obsahuje informace o konkrétním parametru pro úlohu vygenerovanou UsingTask TaskFactory.
ms.custom: SEO-VS-2020
ms.date: 03/13/2017
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
- xml
helpviewer_keywords:
- Parameter element [MSBuild]
- <Parameter> element [MSBuild]
ms.assetid: b273afff-b500-4e97-8cfd-31f39fa64a51
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e7aa8809cbce8f07e18666afb1734026fdc9694b
ms.sourcegitcommit: 1a36533f385e50c05f661f440380fda6386ed3c1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/30/2020
ms.locfileid: "93048881"
---
# <a name="parameter-element"></a>Parameter – element

Obsahuje informace o konkrétním parametru pro úkol, který je generován pomocí `UsingTask` `TaskFactory` .  Název prvku je název parametru.  Další informace naleznete v tématu [UsingTask element (MSBuild)](../msbuild/usingtask-element-msbuild.md).

 \<Project> \<UsingTask>
 \<ParameterGroup>
 \<Parameter>

## <a name="syntax"></a>Syntax

```xml
<ParameterGroup ParameterType="SystemType"
    Output="true/false"
    Required="true/false" />
```

## <a name="attributes-and-elements"></a>Atributy a elementy

 Následující části popisují atributy, podřízené prvky a nadřazené prvky.

### <a name="attributes"></a>Atributy

|Atribut|Popis|
|---------------|-----------------|
|`ParameterType`|Nepovinný atribut.<br /><br /> Typ rozhraní .NET parametru, například `System.String` .|
|`Output`|Volitelný atribut typu Boolean.<br /><br /> Pokud `true` je tento parametr výstupním parametrem pro úlohu. Výchozí hodnota je `false`.|
|`Required`|Volitelný atribut typu Boolean.<br /><br /> Pokud `true` je tento parametr požadovaným parametrem pro úlohu. Výchozí hodnota je `false`.|

### <a name="child-elements"></a>Podřízené prvky

 Žádné

### <a name="parent-elements"></a>Nadřazené prvky

|Element|Popis|
|-------------|-----------------|
|[ParameterGroup –](../msbuild/parametergroup-element.md)|Obsahuje volitelný seznam parametrů, které budou přítomny u úlohy vygenerované pomocí `UsingTask` `TaskFactory` .|

## <a name="example"></a>Příklad

 Následující příklad ukazuje, jak použít `Parameter` element.

```xml
<UsingTask TaskName="MyTask" AssemblyName="My.Assembly" TaskFactory="MyTaskFactory">
       <ParameterGroup>
              <Parameter1 ParameterType="System.String" Required="False" Output="False"/>
              <Parameter2 ParameterType="System.Int" Required="True" Output="False"/>
             ...
</ParameterGroup>
       <Task Evaluate="true">
       ... Task factory-specific data ...
       </Task>
</UsingTask>
```

## <a name="see-also"></a>Viz také

- [Úlohy](../msbuild/msbuild-tasks.md)
- [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)
- [Referenční dokumentace schématu souboru projektu](../msbuild/msbuild-project-file-schema-reference.md)
