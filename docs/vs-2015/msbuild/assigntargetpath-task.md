---
title: Assigntargetpath – úloha | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: msbuild
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
ms.assetid: 0e830e31-3bcf-4259-b2a8-a5df49b92d51
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: f7bf12e9f6c90ce544205370a8ed26440388b0a6
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68187014"
---
# <a name="assigntargetpath-task"></a>AssignTargetPath – úloha
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Tento úkol přijímá seznam souborů a přidává `<TargetPath>` atributy, pokud již nejsou určeny.  
  
## <a name="task-parameters"></a>Parametry úlohy  
 Následující tabulka popisuje parametry `AssignTargetPath` úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`RootFolder`|Volitelné `string` vstupního parametru.<br /><br /> Obsahuje cestu ke složce obsahující cílové odkazy.|  
|`Files`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` vstupního parametru.<br /><br /> Obsahuje seznam příchozích souborů.|  
|`AssignedFiles`|volitelná,<br /><br /> <xref:Microsoft.Build.Framework.ITaskItem> `[]` Výstupní parametr.<br /><br /> Obsahuje výsledný seznam souborů.|  
  
## <a name="remarks"></a>Poznámky  
 Kromě výše uvedených parametrů zdědí tento úkol parametry ze <xref:Microsoft.Build.Tasks.TaskExtension> třída, která sama dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrů a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).  
  
## <a name="example"></a>Příklad  
 Následující příklad provede `AssignTargetPath` úkolů ke konfiguraci projektu.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <Target Name="MyProject">  
        <AssignTargetPath  
RootFolder="Resources"  
            Files="@(ResourceFiles)"  
            <Output TaskParameter="AssignedFiles"  
                ItemName="OutAssignedFiles"/>  
        </AssignTargetPath>  
    </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Viz také  
 [Úlohy](../msbuild/msbuild-tasks.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)
