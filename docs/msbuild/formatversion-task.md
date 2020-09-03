---
title: Úloha FormatVersion – | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
ms.assetid: 96e692f6-b581-46ca-8cc9-441a1861e371
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 250c73ce0395f278b72c18605f1666290670e20a
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "77634107"
---
# <a name="formatversion-task"></a>FormatVersion – úloha

Připojí číslo revize k číslu verze.

- Případ #1: vstup: verze = \<undefined> ;  Revize = \<don't care> ;   Výstup: OutputVersion = "1.0.0.0"

- Case #2: vstup: Version = "1.0.0. *" Revision = "5" Output: OutputVersion = "1.0.0.5"

- Případ #3: vstup: verze = "1.0.0.0" revize = \<don't care> ;  Výstup: OutputVersion = "1.0.0.0"

## <a name="parameters"></a>Parametry

 Následující tabulka popisuje parametry `FormatVersion` úkolu.

|Parametr|Popis|
|---------------|-----------------|
|`FormatType`|Volitelný `String` parametr.<br /><br /> Určuje typ formátu.<br /><br /> -"Version" = Version.<br />-"Path" = Replace "." s "_";|
|`OutputVersion`|Volitelný `String` výstupní parametr.<br /><br /> Určuje výstupní verzi, která obsahuje číslo revize.|
|`Revision`|Volitelný `Int32` parametr.<br /><br /> Určuje revizi, která se má připojit k verzi.|
|`Version`|Volitelný `String` parametr.<br /><br /> Určuje řetězec čísla verze, který má být zformátován.|

## <a name="remarks"></a>Poznámky

 Kromě parametrů, které jsou uvedeny v tabulce, tato úloha dědí parametry z <xref:Microsoft.Build.Tasks.TaskExtension> třídy, která sama dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrů a jejich popis naleznete v tématu [TaskExtension – Base Class](../msbuild/taskextension-base-class.md).

## <a name="see-also"></a>Viz také

- [Úlohy](../msbuild/msbuild-tasks.md)
- [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)
