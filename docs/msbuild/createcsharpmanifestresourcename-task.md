---
title: Úloha CreateCSharpManifestResourceName – | Microsoft Docs
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
ms.openlocfilehash: e8e72ef282911ecb36fb9a16838f6cc311e253e1
ms.sourcegitcommit: 96737c54162f5fd5c97adef9b2d86ccc660b2135
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/26/2020
ms.locfileid: "77634354"
---
# <a name="createcsharpmanifestresourcename-task"></a>CreateCSharpManifestResourceName – úloha

C#Vytvoří název manifestu stylu z daného názvu souboru *. resx* nebo jiného prostředku.

## <a name="parameters"></a>Parametry

 Následující tabulka popisuje parametry [úlohy CreateCSharpManifestResourceName –](../msbuild/createcsharpmanifestresourcename-task.md).

| Parametr | Popis |
| - | - |
| `ManifestResourceNames` | <xref:Microsoft.Build.Framework.ITaskItem> `[]` výstupní parametr s oprávněními jen pro čtení.<br /><br /> Výsledné názvy manifestu. |
| `ResourceFiles` | Vyžaduje se `String` parametr.<br /><br /> Název souboru prostředků, ze kterého má být vytvořen název C# manifestu. |
| `RootNamespace` | Volitelný parametr `String`.<br /><br /> Kořenový obor názvů souboru prostředků, který se obvykle povede ze souboru projektu. Může být `null`. |
| `PrependCultureAsDirectory` | Volitelný parametr `Boolean`.<br /><br /> Pokud `true`, název jazykové verze se přidá jako název adresáře těsně před názvem prostředku manifestu. Výchozí hodnota je `true`. |
| `ResourceFilesWithManifestResourceNames` | Volitelný výstupní parametr `String` jen pro čtení.<br /><br /> Vrátí název souboru prostředků, který teď obsahuje název prostředku manifestu. |

## <a name="remarks"></a>Poznámky

 [Úloha CreateVisualBasicManifestResourceName –](../msbuild/createvisualbasicmanifestresourcename-task.md) určuje vhodný název prostředku manifestu, který se má přiřadit k danému souboru *. resx* nebo jinému souboru prostředků. Úloha poskytuje logický název souboru prostředků a pak ho připojí k výstupnímu parametru jako metadata.

 Kromě výše uvedených parametrů Tato úloha dědí parametry z <xref:Microsoft.Build.Tasks.TaskExtension> třídy, které sama dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrů a jejich popis naleznete v tématu [TaskExtension – Base Class](../msbuild/taskextension-base-class.md).

## <a name="see-also"></a>Viz také

- [Úlohy](../msbuild/msbuild-tasks.md)
- [Odkaz na úkol](../msbuild/msbuild-task-reference.md)
