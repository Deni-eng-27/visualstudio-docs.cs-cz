---
title: Assigntargetpath – úloha | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
ms.assetid: 0e830e31-3bcf-4259-b2a8-a5df49b92d51
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 21678dd573030076d7248dfb7bbf47ea412cecae
ms.sourcegitcommit: 01334abf36d7e0774329050d34b3a819979c95a2
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/07/2019
ms.locfileid: "55853453"
---
# <a name="assigntargetpath-task"></a>Assigntargetpath – úloha
Tento úkol přijímá seznam souborů a přidá `<TargetPath>` atributy, pokud již nejsou určeny.

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

## <a name="see-also"></a>Viz také:
[Úlohy](../msbuild/msbuild-tasks.md)  
[Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)
