---
title: Úloha CreateCSharpManifestResourceName – | Microsoft Docs
description: Pomocí úlohy MSBuild CreateCSharpManifestResourceName – můžete vytvořit název manifestu ve stylu C# z daného názvu souboru. resx nebo jiného prostředku.
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, CreateCSharpManifestResourceName task
- CreateCSharpManifestResourceName task [MSBuild]
ms.assetid: 2ace88c1-d757-40a7-8158-c1d3f5ff0511
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f13293a6967456b153d14464b65182153eca2549
ms.sourcegitcommit: bd9417123c6ef67aa2215307ba5eeec511e43e02
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/28/2020
ms.locfileid: "92796040"
---
# <a name="createcsharpmanifestresourcename-task"></a>CreateCSharpManifestResourceName – úloha

Vytvoří název manifestu ve stylu C# z daného názvu souboru *. resx* nebo jiného prostředku.

## <a name="parameters"></a>Parametry

 Následující tabulka popisuje parametry [úlohy CreateCSharpManifestResourceName –](../msbuild/createcsharpmanifestresourcename-task.md).

| Parametr | Popis |
| - | - |
| `ManifestResourceNames` | <xref:Microsoft.Build.Framework.ITaskItem>`[]`výstup parametru jen pro čtení<br /><br /> Výsledné názvy manifestu. |
| `ResourceFiles` | Požadovaný parametr `String`.<br /><br /> Název souboru prostředků, ze kterého má být vytvořen název manifestu jazyka C#. |
| `RootNamespace` | Volitelný `String` parametr.<br /><br /> Kořenový obor názvů souboru prostředků, který se obvykle povede ze souboru projektu. Může být `null` . |
| `PrependCultureAsDirectory` | Volitelný `Boolean` parametr.<br /><br /> Pokud `true` je název jazykové verze přidán jako název adresáře těsně před názvem prostředku manifestu. Výchozí hodnota je `true`. |
| `ResourceFilesWithManifestResourceNames` | Volitelný výstupní parametr jen pro čtení `String` .<br /><br /> Vrátí název souboru prostředků, který teď obsahuje název prostředku manifestu. |

## <a name="remarks"></a>Poznámky

 [Úloha CreateVisualBasicManifestResourceName –](../msbuild/createvisualbasicmanifestresourcename-task.md) určuje vhodný název prostředku manifestu, který se má přiřadit k danému souboru *. resx* nebo jinému souboru prostředků. Úloha poskytuje logický název souboru prostředků a pak ho připojí k výstupnímu parametru jako metadata.

 Kromě výše uvedených parametrů Tato úloha dědí parametry z <xref:Microsoft.Build.Tasks.TaskExtension> třídy, která sama dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrů a jejich popis naleznete v tématu [TaskExtension – Base Class](../msbuild/taskextension-base-class.md).

## <a name="see-also"></a>Viz také

- [Úlohy](../msbuild/msbuild-tasks.md)
- [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)
