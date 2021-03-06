---
title: Úloha ResolveManifestFiles – | Microsoft Docs
description: Naučte se, jak MSBuild používá úlohu ResolveManifestFiles – k řešení položek v procesu sestavení do souborů pro generování manifestu.
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- ResolveManifestFiles task [MSBuild]
- MSBuild, ResolveManifestFiles task
ms.assetid: e1e14f67-9b69-433f-94d4-a783a68676b2
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ca5b74b32faba4937a821503af3665d1ec1d72c9
ms.sourcegitcommit: 1a36533f385e50c05f661f440380fda6386ed3c1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/30/2020
ms.locfileid: "93048559"
---
# <a name="resolvemanifestfiles-task"></a>ResolveManifestFiles – úloha

Řeší následující položky v procesu sestavení do souborů pro generování manifestu: sestavené položky, závislosti, satelity, obsah, symboly ladění a dokumentace.

## <a name="parameters"></a>Parametry

 Následující tabulka popisuje parametry `ResolveManifestFiles` úkolu.

|Parametr|Popis|
|---------------|-----------------|
|`DeploymentManifestEntryPoint`|Volitelný <xref:Microsoft.Build.Framework.ITaskItem> parametr.<br /><br /> Určuje název manifestu nasazení.|
|`EntryPoint`|Volitelný <xref:Microsoft.Build.Framework.ITaskItem> parametr.<br /><br /> Určuje spravované sestavení nebo odkaz manifestu ClickOnce, který je vstupním bodem manifestu.|
|`ExtraFiles`|Volitelný <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametr.<br /><br /> Určuje další soubory.|
|`ManagedAssemblies`|Volitelný <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametr.<br /><br /> Určuje spravovaná sestavení.|
|`NativeAssemblies`|Volitelný <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametr.<br /><br /> Určuje nativní sestavení.|
|`OutputAssemblies`|Volitelný <xref:Microsoft.Build.Framework.ITaskItem> `[]` výstupní parametr.<br /><br /> Určuje generovaná sestavení.|
|`OutputDeploymentManifestEntryPoint`|Volitelný <xref:Microsoft.Build.Framework.ITaskItem> výstupní parametr.<br /><br /> Určuje výstupní vstupní bod manifestu nasazení.|
|`OutputEntryPoint`|Volitelný <xref:Microsoft.Build.Framework.ITaskItem> výstupní parametr.<br /><br /> Určuje výstupní vstupní bod.|
|`OutputFiles`|Volitelný <xref:Microsoft.Build.Framework.ITaskItem> `[]` výstupní parametr.<br /><br /> Určuje výstupní soubory.|
|`PublishFiles`|Volitelný <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametr.<br /><br /> Určuje soubory pro publikování.|
|`SatelliteAssemblies`|Volitelný <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametr.<br /><br /> Určuje satelitní sestavení.|
|`SigningManifests`|Volitelný `Boolean` parametr.<br /><br /> Pokud `true` jsou manifesty podepsány.|
|`TargetCulture`|Volitelný `String` parametr.<br /><br /> Určuje cílovou jazykovou verzi pro satelitní sestavení.|
|`TargetFrameworkVersion`|Volitelný `String` parametr.<br /><br /> Určuje cílovou verzi .NET Framework.|

## <a name="remarks"></a>Poznámky

 Kromě parametrů, které jsou uvedeny v tabulce, tato úloha dědí parametry z <xref:Microsoft.Build.Tasks.TaskExtension> třídy, která sama dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrů a jejich popis naleznete v tématu [TaskExtension – Base Class](../msbuild/taskextension-base-class.md).

## <a name="see-also"></a>Viz také

- [Úlohy](../msbuild/msbuild-tasks.md)
- [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)
