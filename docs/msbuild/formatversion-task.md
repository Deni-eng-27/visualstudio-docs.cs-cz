---
title: Formatversion – úloha | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
ms.assetid: 96e692f6-b581-46ca-8cc9-441a1861e371
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: cc1651ae769a9dbe8ef8fbd9b8a1a50dd83ea0f6
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56640711"
---
# <a name="formatversion-task"></a>Formatversion – úloha
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

## <a name="see-also"></a>Viz také:
- [Úlohy](../msbuild/msbuild-tasks.md)
- [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)