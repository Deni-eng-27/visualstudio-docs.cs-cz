---
title: Element Task of UsingTask (MSBuild) | Microsoft Docs
description: Přečtěte si o elementu Task UsingTask nástroje MSBuild, který obsahuje data předávaná UsingTask TaskFactory.
ms.custom: SEO-VS-2020
ms.date: 03/13/2017
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- Task element [MSBuild]
- <Task> element [MSBuild]
ms.assetid: 49d8741b-f1ea-4470-94fd-a1ac27341a6a
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f99452021b0efef1e5df305e984c684f3f446905
ms.sourcegitcommit: 1a36533f385e50c05f661f440380fda6386ed3c1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/30/2020
ms.locfileid: "93047888"
---
# <a name="task-element-of-usingtask-msbuild"></a>Element Task pro UsingTask (MSBuild)

Obsahuje data předávaná do `UsingTask` `TaskFactory` . Další informace naleznete v tématu [UsingTask element (MSBuild)](../msbuild/usingtask-element-msbuild.md).

 \<Project> \<UsingTask>
 \<Task>

## <a name="syntax"></a>Syntax

```xml
<Task Evaluate="true/false" />
```

## <a name="attributes-and-elements"></a>Atributy a elementy

 Následující části popisují atributy, podřízené prvky a nadřazené prvky.

### <a name="attributes"></a>Atributy

|Atribut|Popis|
|---------------|-----------------|
|`Evaluate`|Volitelný atribut typu Boolean.<br /><br /> Pokud `true` Nástroj MSBuild vyhodnocuje všechny vnitřní prvky a rozbalí položky a vlastnosti před tím, než předává informace do `TaskFactory` objektu při vytvoření instance úkolu.|

### <a name="child-elements"></a>Podřízené prvky

|Element|Popis|
|-------------|-----------------|
|Data|Text mezi `Task` značkami se posílá do `TaskFactory` .|

### <a name="parent-elements"></a>Nadřazené prvky

| Element | Popis |
| - | - |
| [UsingTask](../msbuild/usingtask-element-msbuild.md) | Poskytuje způsob, jak registrovat úlohy v nástroji MSBuild. V projektu může být nula nebo více `UsingTask` prvků. |

## <a name="example"></a>Příklad

 Následující příklad ukazuje, jak použít `Task` element s `Evaluate` atributem.

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
