---
title: "Assigntargetpath – úloha | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
ms.assetid: 0e830e31-3bcf-4259-b2a8-a5df49b92d51
caps.latest.revision: "4"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: dac2cd390d6b7b706785d4807e659ca44620def9
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="assigntargetpath-task"></a>AssignTargetPath – úloha
Tato úloha přijímá seznam souborů a přidá `<TargetPath>` atributy, když už nejsou zadané.  
  
## <a name="task-parameters"></a>Parametry úlohy  
 Následující tabulka popisuje parametry `AssignTargetPath` úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`RootFolder`|Volitelné `string` vstupní parametr.<br /><br /> Obsahuje cestu ke složce, která obsahuje cílové odkazy.|  
|`Files`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` vstupní parametr.<br /><br /> Příchozí seznam souborů, které obsahuje.|  
|`AssignedFiles`|Nepovinné<br /><br /> <xref:Microsoft.Build.Framework.ITaskItem>`[]` výstupní parametr.<br /><br /> Výsledný seznam souborů, které obsahuje.|  
  
## <a name="remarks"></a>Poznámky  
 Kromě výše uvedených parametrů tato úloha dědí parametry z <xref:Microsoft.Build.Tasks.TaskExtension> třída, které dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrech a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).  
  
## <a name="example"></a>Příklad  
 Následující příklad spustí `AssignTargetPath` úlohy konfigurace projektu.  
  
```xml  
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