---
title: Error – úloha | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#Error
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- Error task [MSBuild]
- MSBuild, Error task
ms.assetid: e96a90ee-a8ae-4e5b-8ef2-b5cf5fedd8b2
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d2cae930f1d4cd07c63d7c40e966363ea92c1a84
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="error-task"></a>Error – úloha
Zastaví sestavení a protokoly chybu založené na příkazu vyhodnotí podmíněného.  
  
## <a name="parameters"></a>Parametry  
 V následující tabulce jsou popsány parametry `Error` úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`Code`|Volitelné `String` parametr.<br /><br /> Kód chyby pro přidružení k chybě.|  
|`File`|Volitelné `String` parametr.<br /><br /> Název souboru, který obsahuje chybu. Pokud je zadán žádný název souboru, použije se souboru, který obsahuje chyby úlohy.|  
|`HelpKeyword`|Volitelné `String` parametr.<br /><br /> Klíčové slovo nápovědy pro přidružení k chybě.|  
|`Text`|Volitelné `String` parametr.<br /><br /> Text chyby, [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] protokoly, pokud `Condition` vyhodnocen jako parametr `true`.|  
  
## <a name="remarks"></a>Poznámky  
 `Error` Úloha umožňuje [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] projekty vydávat text chyby protokolovacích nástrojů a zastavit provádění sestavení.  
  
 Pokud `Condition` vyhodnocen jako parametr `true`, sestavení se zastaví a zaznamenána chyba. Pokud `Condition` parametr neexistuje, chyba je zaznamenána do protokolu a sestavení provádění zastaví. Další informace o protokolování naleznete v tématu [získání sestavení protokoly](../msbuild/obtaining-build-logs-with-msbuild.md).  
  
 Kromě výše uvedených parametrů tato úloha dědí parametry z <xref:Microsoft.Build.Tasks.TaskExtension> třída, které dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrech a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu ověřuje, že všechny požadované, jsou nastavené vlastnosti. Pokud nejsou nastavená, vyvolá událost chyby projekt a protokoly hodnotu `Text` parametr `Error` úloh.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <Target Name="ValidateCommandLine">  
        <Error  
            Text=" The 0 property must be set on the command line."  
            Condition="'$(0)' == ''" />  
        <Error  
            Text="The FREEBUILD property must be set on the command line."  
            Condition="'$(FREEBUILD)' == ''" />  
    </Target>  
    ...  
</Project>  
```  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)   
 [Získávání protokolů o sestavení](../msbuild/obtaining-build-logs-with-msbuild.md)