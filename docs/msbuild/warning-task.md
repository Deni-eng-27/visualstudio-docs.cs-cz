---
title: Warning – úloha | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
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
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c2c3b23f9377fff4e820f10b76ed841ff722b15d
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53910179"
---
# <a name="warning-task"></a>Warning – úloha
Protokoly upozornění během sestavení podle Vyhodnocená podmíněném příkazu.  

## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry `Warning` úloh.  


| Parametr | Popis |
|---------------| - |
| `Code` | Volitelné `String` parametru.<br /><br /> Kód upozornění pro přidružení k upozornění. |
| `File` | Volitelné `String` parametru.<br /><br /> Určuje příslušný soubor, pokud existuje. Pokud není žádný soubor zadaný v souboru, který obsahuje upozornění úkolů se používá. |
| `HelpKeyword` | Volitelné `String` parametru.<br /><br /> Klíčové slovo nápovědy pro přidružení k upozornění. |
| `Text` | Volitelné `String` parametru.<br /><br /> Text upozornění, která [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] protokoly, pokud `Condition` vyhodnotí jako parametr `true`. |

## <a name="remarks"></a>Poznámky  
 `Warning` Úloha umožňuje [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] projekty ke kontrole přítomnosti požadovanou konfiguraci nebo vlastnost před pokračováním na další krok sestavení.  

 Pokud `Condition` parametr `Warning` vyhodnotí jako úloha `true`, hodnota `Text` parametr je zaznamenána do protokolu a pokračuje v provádění sestavení. Pokud `Condition` neexistuje parametr, se do protokolu zapíše text upozornění. Další informace o protokolování naleznete v tématu [získat protokoly o sestavení](../msbuild/obtaining-build-logs-with-msbuild.md).  

 Kromě výše uvedených parametrů zdědí tento úkol parametry ze <xref:Microsoft.Build.Tasks.TaskExtension> třída, která sama dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrů a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).  

## <a name="example"></a>Příklad  
 Následující příklad kódu zkontroluje pro vlastnosti, které jsou nastaveny na příkazovém řádku. Pokud neexistují žádná sada vlastností, vyvolá událost upozornění projektu a protokoly hodnotu `Text` parametr `Warning` úloh.  

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

## <a name="see-also"></a>Viz také:  
 [Získání protokolů o sestavení](../msbuild/obtaining-build-logs-with-msbuild.md)   
 [Referenční dokumentace schématu souboru projektu](../msbuild/msbuild-project-file-schema-reference.md)