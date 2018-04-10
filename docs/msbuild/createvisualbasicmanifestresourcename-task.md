---
title: Createvisualbasicmanifestresourcename – úloha | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology: msbuild
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, CreateVisualBasicManifestResourceName task
- CreateVisualBasicManifestResourceName task [MSBuild]
ms.assetid: 251c47b9-de32-414b-a138-bf45290af12e
caps.latest.revision: 8
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 133b1b6cf881d014c93391b316710975a84a2f21
ms.sourcegitcommit: 3b692c9bf332b7b9150901e16daf99a64b599fee
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/10/2018
---
# <a name="createvisualbasicmanifestresourcename-task"></a>CreateVisualBasicManifestResourceName – úloha
Vytvoří [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]-manifestu název stylu z daného RESX název souboru nebo jiný prostředek.  
  
## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry [createvisualbasicmanifestresourcename – úloha](../msbuild/createvisualbasicmanifestresourcename-task.md).  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`ManifestResourceNames`|<xref:Microsoft.Build.Framework.ITaskItem> `[]` výstupní parametr jen pro čtení.<br /><br /> Výsledný manifestu názvy.|  
|`ResourceFiles`|Požadované `String` parametr.<br /><br /> Název souboru prostředků, ze které chcete vytvořit [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] názvu manifestu.|  
|`RootNamespace`|Volitelné `String` parametr.<br /><br /> Kořenového oboru názvů souboru prostředků, obvykle převzat ze souboru projektu. Může být `null`.|  
|`PrependCultureAsDirectory`|Volitelné `Boolean` parametr.<br /><br /> Pokud `true`, název jazykové verze je přidán jako název adresáře těsně před název prostředku manifestu. Výchozí hodnota je `true`.|  
|`ResourceFilesWithManifestResourceNames`|Volitelné jen pro čtení `String` výstupní parametr.<br /><br /> Vrátí název souboru prostředků, který teď zahrnuje název prostředku manifestu.|  
  
## <a name="remarks"></a>Poznámky  
 [Createvisualbasicmanifestresourcename – úloha](../msbuild/createvisualbasicmanifestresourcename-task.md) Určuje název odpovídající prostředku manifestu přiřazení k dané resx nebo jiný soubor prostředků. Úloha obsahuje logický název souboru prostředků a potom ji připojí k výstupní parametr jako metadata.  
  
 Kromě výše uvedených parametrů tato úloha dědí parametry z <xref:Microsoft.Build.Tasks.TaskExtension> třída, které dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrech a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).  
  
## <a name="see-also"></a>Viz také  
 [Úlohy](../msbuild/msbuild-tasks.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)