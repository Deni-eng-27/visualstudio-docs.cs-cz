---
title: Odstranit úlohu | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#Delete
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- Delete task [MSBuild]
- MSBuild, Delete task
ms.assetid: 916bb2e3-3017-4828-ae27-c0b5c99bbb48
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 69f6be4c80519b023d3f11c28f3d5f5b2bf8f8e1
ms.sourcegitcommit: bf2e9d4ff38bf5b62b8af3da1e6a183beb899809
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2020
ms.locfileid: "77557964"
---
# <a name="delete-task"></a>Delete – úloha
Odstraní zadané soubory.

## <a name="parameters"></a>Parametry
Následující tabulka popisuje parametry úlohy `Delete`.

|Parametr|Popis|
|---------------|-----------------|
|`DeletedFiles`|Volitelný <xref:Microsoft.Build.Framework.ITaskItem>parametr Output `[]`.<br /><br /> Určuje soubory, které se úspěšně odstranily.|
|`Files`|Požadovaný parametr <xref:Microsoft.Build.Framework.ITaskItem>`[]`.<br /><br /> Určuje soubory, které se mají odstranit.|
|`TreatErrorsAsWarnings`|Volitelný parametr `Boolean`<br /><br /> Pokud `true`, chyby se protokolují jako upozornění. Výchozí hodnota je `false`.|

## <a name="remarks"></a>Poznámky
Kromě výše uvedených parametrů Tato úloha dědí parametry z <xref:Microsoft.Build.Tasks.TaskExtension> třídy, které sama dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrů a jejich popis naleznete v tématu [TaskExtension – Base Class](../msbuild/taskextension-base-class.md).

> [!WARNING]
> Při použití zástupných znaků s úkolem `Delete` buďte opatrní. Nesprávné soubory můžete snadno odstranit pomocí výrazů jako `$(SomeProperty)\**\*.*` nebo `$(SomeProperty)/**/*.*`, zejména pokud je vlastnost vyhodnocena jako prázdný řetězec. v takovém případě se parametr `Files` může vyhodnotit na kořenový adresář jednotky a odstranit mnohem více, než jste chtěli odstranit.

## <a name="example"></a>Příklad
Následující příklad odstraní soubor *MyApp. pdb*.

```xml
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">

    <PropertyGroup>
        <AppName>MyApp</AppName>
    </PropertyGroup>

    <Target Name="DeleteFiles">
        <Delete Files="$(AppName).pdb" />
    </Target>
</Project>
```

## <a name="see-also"></a>Viz také
- [Úlohy](../msbuild/msbuild-tasks.md)
- [Odkaz na úkol](../msbuild/msbuild-task-reference.md)
