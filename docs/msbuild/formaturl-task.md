---
title: Úloha FormatUrl – | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, FormatUrl task
- FormatUrl task [MSBuild]
ms.assetid: 81114b67-520f-43b5-8891-224f68a78516
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 5fcd4ed0c60d615f0c213e1af5099c5e94a9b485
ms.sourcegitcommit: 96737c54162f5fd5c97adef9b2d86ccc660b2135
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/26/2020
ms.locfileid: "77634120"
---
# <a name="formaturl-task"></a>FormatUrl – úloha

Převede adresu URL na správný formát adresy URL.

## <a name="parameters"></a>Parametry

 Následující tabulka popisuje parametry úlohy `FormatUrl`.

|Parametr|Popis|
|---------------|-----------------|
|`InputUrl`|Volitelný parametr `String`.<br /><br /> Určuje adresu URL, která má být naformátovaná.|
|`OutputUrl`|Volitelný výstupní parametr `String`.<br /><br /> Určuje formátovanou adresu URL.|

## <a name="remarks"></a>Poznámky

 Kromě toho, že mají parametry, které jsou uvedeny v tabulce, tato úloha dědí parametry z třídy <xref:Microsoft.Build.Tasks.TaskExtension>, kterou sám dědí z třídy <xref:Microsoft.Build.Utilities.Task>. Seznam těchto dalších parametrů a jejich popis naleznete v tématu [TaskExtension – Base Class](../msbuild/taskextension-base-class.md).

## <a name="see-also"></a>Viz také

- [Úlohy](../msbuild/msbuild-tasks.md)
- [Odkaz na úkol](../msbuild/msbuild-task-reference.md)