---
title: Úloha XslTransformation – | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, XslTransformation task
- XslTransformation task [MSBuild]
ms.assetid: 6f3a7d81-3ae3-4703-9a06-870b32b69d80
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 90b56d3b36545ecfe97015fc301ce3ce72e781ba
ms.sourcegitcommit: d233ca00ad45e50cf62cca0d0b95dc69f0a87ad6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/01/2020
ms.locfileid: "75588366"
---
# <a name="xsltransformation-task"></a>XslTransformation – úloha
Transformuje vstup XML pomocí XSLT nebo zkompilovaného souboru XSLT a výstupy na výstupní zařízení nebo soubor.

## <a name="parameters"></a>Parametry
 Následující tabulka popisuje parametry úlohy `XslTransformation`.

|Parametr|Popis|
|---------------|-----------------|
|`OutputPaths`|Požadovaný parametr <xref:Microsoft.Build.Framework.ITaskItem>`[]`.<br /><br /> Určuje výstupní soubory pro transformaci XML.|
|`Parameters`|Volitelný parametr `String`.<br /><br /> Určuje parametry pro vstupní dokument XSLT.|
|`XmlContent`|Volitelný parametr `String`.<br /><br /> Určuje vstup XML jako řetězec.|
|`XmlInputPaths`|Volitelný <xref:Microsoft.Build.Framework.ITaskItem>`[]` parametr.<br /><br /> Určuje vstupní soubory XML.|
|`XslCompiledDllPath`|Volitelný parametr <xref:Microsoft.Build.Framework.ITaskItem>.<br /><br /> Určuje kompilovaný soubor XSLT.|
|`XslContent`|Volitelný parametr `String`.<br /><br /> Určuje vstup XSLT jako řetězec.|
|`XslInputPath`|Volitelný parametr <xref:Microsoft.Build.Framework.ITaskItem>.<br /><br /> Určuje vstupní soubor XSLT.|

## <a name="remarks"></a>Poznámky
 Kromě toho, že mají parametry, které jsou uvedeny v tabulce, tato úloha dědí parametry z třídy <xref:Microsoft.Build.Tasks.TaskExtension>, kterou sám dědí z třídy <xref:Microsoft.Build.Utilities.Task>. Seznam těchto dalších parametrů a jejich popis naleznete v tématu [TaskExtension – Base Class](../msbuild/taskextension-base-class.md).

## <a name="see-also"></a>Viz také:
- [Úlohy](../msbuild/msbuild-tasks.md)
- [Odkaz na úkol](../msbuild/msbuild-task-reference.md)
