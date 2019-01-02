---
title: Generatetrustinfo – úloha | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, GenerateTrustInfo task
- GenerateTrustInfo task [MSBuild]
ms.assetid: 3ca60816-4bb0-4fef-ae43-ca0bfb63def3
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f2c4c03eba5d0b154ce219daeea3761a001a2198
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53949573"
---
# <a name="generatetrustinfo-task"></a>GenerateTrustInfo – úloha
Generuje důvěryhodnost aplikace z manifestu základní a `TargetZone` a `ExcludedPermissions` parametry.  
  
## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry `GenerateTrustInfo` úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`ApplicationDependencies`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametru.<br /><br /> Určuje závislá sestavení.|  
|`BaseManifest`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> parametru.<br /><br /> Určuje základní manifest generovat důvěryhodnost aplikace z.|  
|`ExcludedPermissions`|Volitelné `String` parametru.<br /><br /> Určuje jednu nebo více hodnot identity oddělených středníkem oprávnění mají být vyloučeny ze sady zóny výchozí oprávnění.|  
|`TargetZone`|Volitelné `String` parametru.<br /><br /> Určuje výchozí oprávnění sadě, který získáte od zásady počítače.|  
|`TrustInfoFile`|Vyžaduje <xref:Microsoft.Build.Framework.ITaskItem> výstupní parametr.<br /><br /> Určuje soubor, který obsahuje informace o vztahu důvěryhodnosti zabezpečení aplikace.|  
  
## <a name="remarks"></a>Poznámky  
 Kromě s parametry, které jsou uvedené v tabulce, zdědí tento úkol parametry ze <xref:Microsoft.Build.Tasks.TaskExtension> třída, která sama dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrů a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).  
  
## <a name="see-also"></a>Viz také:  
 [Úlohy](../msbuild/msbuild-tasks.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)