---
title: "Warning – úloha | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#Warning
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- Warning task [MSBuild]
- MSBuild, Warning task
ms.assetid: 96ba5507-8b43-4f54-a1d7-9b15644dd56c
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: ca4e9906d31468b028f1ad9a39c196bd54e3fb9e
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/09/2018
---
# <a name="warning-task"></a>Warning – úloha
Protokoly upozornění během sestavení založené na příkazu vyhodnotí podmíněného.  
  
## <a name="parameters"></a>Parametry  
 V následující tabulce jsou popsány parametry `Warning` úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`Code`|Volitelné `String` parametr.<br /><br /> Kód upozornění pro přidružení s upozorněním.|  
|`File`|Volitelné `String` parametr.<br /><br /> Určuje soubor relevantní, pokud existuje. Pokud je k dispozici žádný soubor, použije se souboru, který obsahuje úlohu upozornění.|  
|`HelpKeyword`|Volitelné `String` parametr.<br /><br /> Klíčové slovo nápovědy k přidružení s upozorněním.|  
|`Text`|Volitelné `String` parametr.<br /><br /> Text upozornění, [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] protokoly, pokud `Condition` vyhodnocen jako parametr `true`.|  
  
## <a name="remarks"></a>Poznámky  
 `Warning` Úloha umožňuje [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] projekty tak, aby kontrolovat přítomnost požadovanou konfiguraci nebo vlastnost před pokračováním na další krok sestavení.  
  
 Pokud `Condition` parametr `Warning` úloh se vyhodnocuje `true`, hodnota `Text` zaznamená parametr a sestavení bude pokračovat v provádění. Pokud `Condition` parametr neobsahuje případech, se do protokolu zapíše text upozornění. Další informace o protokolování naleznete v tématu [získání sestavení protokoly](../msbuild/obtaining-build-logs-with-msbuild.md).  
  
 Kromě výše uvedených parametrů tato úloha dědí parametry z <xref:Microsoft.Build.Tasks.TaskExtension> třída, které dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrech a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu zkontroluje vlastnosti, které jsou nastaveny na příkazovém řádku. Pokud není nastavený žádný vlastnosti se vyvolá událost upozornění projekt a protokoly hodnotu `Text` parametr `Warning` úloh.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <Target Name="ValidateCommandLine">  
        <Warning  
            Text=" The 0 property was not set on the command line."  
            Condition="'$(0)' == ''" />  
        <Warning  
            Text=" The FREEBUILD property was not set on the command line."  
            Condition="'$(FREEBUILD)' == ''" />  
    </Target>  
    ...  
</Project>  
```  
  
## <a name="see-also"></a>Viz také  
 [Získávání protokolů o sestavení](../msbuild/obtaining-build-logs-with-msbuild.md)   
 [Referenční dokumentace schématu souboru projektu](../msbuild/msbuild-project-file-schema-reference.md)