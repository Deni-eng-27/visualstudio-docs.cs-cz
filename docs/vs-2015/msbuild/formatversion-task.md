---
title: Formatversion – úloha | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: msbuild
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
ms.assetid: 96e692f6-b581-46ca-8cc9-441a1861e371
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 7fbd03676d69dde5f9a6d169739a25e7b5e1b82e
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54755122"
---
# <a name="formatversion-task"></a>FormatVersion – úloha
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
Číslo revize připojí číslo verze.  
  
-   Případ #1: Vstup: Verze =\<nedefinované >;  Revize =\<nezáleží na tom >;   Výstup: OutputVersion="1.0.0.0"  
  
-   Případ #2: Vstup: Verze = "1.0.0.*" revize = "5" výstup: OutputVersion="1.0.0.5"  
  
-   Případ #3: Vstup: Verze = "1.0.0.0" Revize =\<nezáleží na tom >;  Výstup: OutputVersion="1.0.0.0"  
  
## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry `FormatVersion` úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`FormatType`|Volitelné `String` parametru.<br /><br /> Určuje typ formátu.<br /><br /> -"Verze" = verze.<br />-"Cesty"= nahradit"." s "_";|  
|`OutputVersion`|Volitelné `String` výstupní parametr.<br /><br /> Určuje verzi výstup, který obsahuje číslo revize.|  
|`Revision`|Volitelné `Int32` parametru.<br /><br /> Určuje revizi chcete připojit k verzi.|  
|`Version`|Volitelné `String` parametru.<br /><br /> Určuje řetězec, číslo verze pro formátování.|  
  
## <a name="remarks"></a>Poznámky  
 Kromě s parametry, které jsou uvedené v tabulce, zdědí tento úkol parametry ze <xref:Microsoft.Build.Tasks.TaskExtension> třída, která sama dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrů a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).  
  
## <a name="see-also"></a>Viz také  
 [Úlohy](../msbuild/msbuild-tasks.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)
