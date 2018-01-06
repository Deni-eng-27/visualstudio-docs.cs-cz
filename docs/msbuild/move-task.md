---
title: "Move – úloha | Microsoft Docs"
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
helpviewer_keywords:
- MSBuild, Move task
- Move task [MSBuild]
ms.assetid: d1405347-1309-4f18-b565-905408093d59
caps.latest.revision: "4"
author: kempb
ms.author: kempb
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 521a5239e47ffcab4d93c2cd2a46c30f881b0abd
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="move-task"></a>Move – úloha
Soubory přesune do nového umístění.  
  
## <a name="parameters"></a>Parametry  
 V následující tabulce jsou popsány parametry `Move` úloh.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`DestinationFiles`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` výstupní parametr.<br /><br /> Určuje seznam souborů pro zdrojové soubory pro přesun. Tento seznam se očekává mapování 1: 1 do seznamu, který je uveden v `SourceFiles` parametr. To znamená, první soubor zadaný v `SourceFiles` přesunou do zadaného v první umístění `DestinationFiles`, a tak dále.|  
|`DestinationFolder`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> parametr.<br /><br /> Určuje adresář, do které chcete přesunout soubory.|  
|`MovedFiles`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` výstupní parametr.<br /><br /> Obsahuje položky, které byly úspěšně přesunuty.|  
|`OverwriteReadOnlyFiles`|Volitelné `Boolean` parametr.<br /><br /> Pokud `true`, přepíše soubory i v případě, že jsou označeny jako jen pro čtení souborů.|  
|`SourceFiles`|Požadovaný parametr <xref:Microsoft.Build.Framework.ITaskItem>`[]`.<br /><br /> Určuje soubory, které chcete přesunout.|  
  
## <a name="remarks"></a>Poznámky  
 Buď `DestinationFolder` parametr nebo `DestinationFiles` parametr musí být zadaný, ale ne pomocí obou. Jsou-li zadány oba parametry, úloha se nezdaří a je zaznamenána chyba.  

 `Move` Úloh vytvoří podle potřeby pro soubory požadované cílové složky.

 Kromě s parametry, které jsou uvedené v tabulce, zdědí tento úkol parametry z <xref:Microsoft.Build.Tasks.TaskExtension> třída, které dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrech a jejich popisy najdete v tématu [taskextension – základní třída](../msbuild/taskextension-base-class.md).  
  
## <a name="see-also"></a>Viz také  
 [Úlohy](../msbuild/msbuild-tasks.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)
