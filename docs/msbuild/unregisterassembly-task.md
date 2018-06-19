---
title: Unregisterassembly – úloha | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#UnregisterAssembly
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, UnregisterAssembly task
- UnregisterAssembly task [MSBuild]
ms.assetid: 04f549dd-3591-4dda-9c3a-cf6ede9df2c3
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5fb2ef935015e7bd1058868b546543a789d7cec2
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
ms.locfileid: "31576830"
---
# <a name="unregisterassembly-task"></a>UnregisterAssembly – úloha
Zruší registraci na zadaná sestavení pro účely zprostředkovatele komunikace s objekty COM. Provádí opak [registerassembly – úloha](../msbuild/registerassembly-task.md).  
  
## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry `UnregisterAssembly` úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`Assemblies`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametr.<br /><br /> Určuje sestavení, které chcete se zrušit registraci.|  
|`AssemblyListFile`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> parametr.<br /><br /> Obsahuje informace o stavu mezi `RegisterAssembly` úloh a `UnregisterAssembly` úloh. To brání pokusu o zrušení registrace sestavení, které se nepodařilo zaregistrovat v úlohu `RegisterAssembly` úloh.<br /><br /> Pokud je tento parametr zadán, `Assemblies` a `TypeLibFiles` parametry jsou ignorovány.|  
|`TypeLibFiles`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` výstupní parametr.<br /><br /> Zrušení registrace knihovny zadaného typu ze zadaného sestavení. **Poznámka:** tento parametr je nutné v případě, že je název souboru knihovny typ jiný než název sestavení.|  
  
## <a name="remarks"></a>Poznámky  
 Není nutné, aby sestavení existuje pro tuto úlohu úspěšný. Když zkusíte se zrušit registraci sestavení, které neexistuje, bude úloha úspěšné s upozorněním. K tomu dochází, protože je úloha této úlohy můžete odebrat registraci sestavení z registru. Pokud sestavení neexistuje, není v registru, a proto byla úloha úspěšná.  
  
 Kromě výše uvedených parametrů tato úloha dědí parametry z <xref:Microsoft.Build.Tasks.AppDomainIsolatedTaskExtension> třída, které dědí z <xref:System.MarshalByRefObject> třídy. `MarshalByRefObject` Třída poskytuje stejné funkce jako <xref:Microsoft.Build.Utilities.Task> třídy, ale může být vytvořena instance, v jeho vlastní domény aplikace.  
  
## <a name="example"></a>Příklad  
 Následující příklad používá `UnregisterAssembly` úloh se zrušit registraci sestavení v cestě určeného `OutputPath` a `FileName` vlastnosti, pokud existuje.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <PropertyGroup>  
        <OutputPath>\Output\</OutputPath>  
        <FileName>MyFile.dll</FileName>  
    </PropertyGroup>  
    <Target Name="UnregisterAssemblies">  
        <UnregisterAssembly  
            Condition="Exists('$(OutputPath)$(FileName)')"  
            Assemblies="$(OutputPath)$(FileName)" />  
    </Target>  
  
</Project>  
```  
  
## <a name="see-also"></a>Viz také  
 [Registerassembly – úloha](../msbuild/registerassembly-task.md)   
 [Úlohy](../msbuild/msbuild-tasks.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)