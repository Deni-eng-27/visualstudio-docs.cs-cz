---
title: Updatemanifest – úloha | Dokumentace Microsoftu
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
- MSBuild, UpdateManifest task
- UpdateManifest task [MSBuild]
ms.assetid: 1291fd33-b89e-4e15-8fb1-69f9625cf2d2
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 54364f40c25deb4a32431c42f74d76bbdd42b155
ms.sourcegitcommit: a83c60bb00bf95e6bea037f0e1b9696c64deda3c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/19/2019
ms.locfileid: "54802144"
---
# <a name="updatemanifest-task"></a>UpdateManifest – úloha
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
Aktualizace vybraných vlastností v manifestu a vzdává.  
  
## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry `UpdateManifest` úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`ApplicationManifest`|Vyžaduje <xref:Microsoft.Build.Framework.ITaskItem> parametru.<br /><br /> Určuje manifest aplikace.|  
|`ApplicationPath`|Vyžaduje `String` parametru.<br /><br /> Určuje cestu k manifestu aplikace.|  
|`InputManifest`|Vyžaduje <xref:Microsoft.Build.Framework.ITaskItem> parametru.<br /><br /> Určuje manifest aktualizovat.|  
|`OutputManifest`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> výstupní parametr.<br /><br /> Určuje manifest, který obsahuje aktualizované vlastnosti.|  
  
## <a name="remarks"></a>Poznámky  
 Kromě s parametry, které jsou uvedené v tabulce, zdědí tento úkol parametry ze <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrů a jejich popisy najdete v tématu [Třída Base úlohy](../msbuild/task-base-class.md).  
  
## <a name="see-also"></a>Viz také  
 [Úlohy](../msbuild/msbuild-tasks.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)
