---
title: Úloha Requiresframework35sp1assembly – | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: msbuild
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- RequiresFramework35SP1Assembly task [MSBuild]
- MSBuild, RequiresFramework35SP1Assembly task
ms.assetid: 755c018a-8a8b-4c94-8aee-3f171fc419e5
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: ada207a619021922b999d0e821ecf27ba48dbb38
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "68158745"
---
# <a name="requiresframework35sp1assembly-task"></a>RequiresFramework35SP1Assembly – úloha
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Určuje, jestli aplikace vyžaduje .NET Framework 3,5 SP1.  
  
## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry `RequiresFramework35SP1Assembly` úkolu.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`Assemblies`|Volitelný <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametr.<br /><br /> Určuje sestavení, na která jsou odkazována v aplikaci.|  
|`CreateDesktopShortcut`|Volitelný `Boolean` parametr.<br /><br /> Pokud `true` se během instalace vytvoří ikona zástupce na ploše.|  
|`DeploymentManifestEntryPoint`|Volitelný <xref:Microsoft.Build.Framework.ITaskItem> parametr.<br /><br /> Určuje název souboru manifestu pro aplikaci.|  
|`EntryPoint`|Volitelný <xref:Microsoft.Build.Framework.ITaskItem> parametr.<br /><br /> Určuje sestavení, které se má provést při spuštění aplikace.|  
|`ErrorReportUrl`|Volitelný `String` parametr.<br /><br /> Určuje web, který se zobrazí v dialogových oknech, které se vyskytují během instalace ClickOnce.|  
|`Files`|Volitelný <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametr.<br /><br /> Určuje seznam souborů, které budou nasazeny při publikování aplikace.|  
|`ReferencedAssemblies`|Volitelný <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametr.<br /><br /> Určuje sestavení, která jsou odkazována v projektu.|  
|`RequiresMinimumFramework35SP1`|Volitelný `Boolean` výstupní parametr.<br /><br /> Pokud `true` aplikace vyžaduje .NET Framework 3,5 SP1.|  
|`SigningManifests`|Volitelný `Boolean` výstupní parametr.<br /><br /> Pokud `true` jsou manifesty ClickOnce podepsány.|  
|`SuiteName`|Volitelný `String` parametr.<br /><br /> Určuje název složky v nabídce **Start** , do které se aplikace nainstaluje.|  
|`TargetFrameworkVersion`|Volitelný `String` parametr.<br /><br /> Určuje verzi .NET Framework, na kterou se tato aplikace zaměřuje.|  
  
## <a name="remarks"></a>Poznámky  
 Kromě parametrů, které jsou uvedeny v tabulce, tato úloha dědí parametry z <xref:Microsoft.Build.Tasks.TaskExtension> třídy, která sama dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrů a jejich popis naleznete v tématu [TaskExtension – Base Class](../msbuild/taskextension-base-class.md).  
  
## <a name="see-also"></a>Viz také  
 [Provádění](../msbuild/msbuild-tasks.md)   
 [Odkaz na úkol](../msbuild/msbuild-task-reference.md)
