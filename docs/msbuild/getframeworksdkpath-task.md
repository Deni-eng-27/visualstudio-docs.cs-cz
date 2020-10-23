---
title: Úloha GetFrameworkSdkPath – | Microsoft Docs
description: Přečtěte si, jak pomocí úlohy MSBuild GetFrameworkSdkPath – načíst cestu k Windows SDK.
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#GetFrameworkSdkPath
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- GetFrameworkSdkPath task [MSBuild]
- MSBuild, GetFrameworkSdkPath task
ms.assetid: 2ef82b98-02b6-40cf-a9b5-f0e882fb5064
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e4061dbe96c84648aacf136c0d59b92a2af037e2
ms.sourcegitcommit: c4927ef8fe239005d7feff6c5a7707c594a7a05c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/22/2020
ms.locfileid: "92436808"
---
# <a name="getframeworksdkpath-task"></a>GetFrameworkSdkPath – úloha

Načte cestu k sadě Windows Software Development Kit (SDK).
## <a name="task-parameters"></a>Parametry úlohy

Následující tabulka popisuje parametry `GetFrameworkSdkPath` úkolu.
Následující tabulka popisuje parametry `GetFrameworkSdkPath` úkolu.

|Parametr|Popis|
|---------------|-----------------|
|`FrameworkSdkVersion20Path`|Volitelný `String` výstupní parametr jen pro čtení.<br /><br /> Vrátí cestu k sadě .NET SDK verze 2,0, pokud je k dispozici. Jinak vrací `String.Empty`.|
|`FrameworkSdkVersion35Path`|Volitelný `String` výstupní parametr jen pro čtení.<br /><br /> Vrátí cestu k sadě .NET SDK verze 3,5, pokud je k dispozici. Jinak vrací `String.Empty`.|
|`FrameworkSdkVersion40Path`|Volitelný `String` výstupní parametr jen pro čtení.<br /><br /> Vrátí cestu k sadě .NET SDK verze 4,0, pokud je k dispozici. Jinak vrací `String.Empty`.|
|`Path`|Volitelný `String` výstupní parametr.<br /><br /> Obsahuje cestu k nejnovější sadě .NET SDK, pokud je k dispozici nějaká verze. Jinak vrací `String.Empty`.|

## <a name="remarks"></a>Poznámky

Kromě výše uvedených parametrů Tato úloha dědí parametry z <xref:Microsoft.Build.Tasks.TaskExtension> třídy, která sama dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam těchto dalších parametrů a jejich popis naleznete v tématu [TaskExtension – Base Class](../msbuild/taskextension-base-class.md).

## <a name="example"></a>Příklad

Následující příklad používá `GetFrameworkSdkPath` úlohu k uložení cesty k Windows SDK ve `SdkPath` Vlastnosti.

```xml
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
    <Target Name="GetPath">
        <GetFrameworkSdkPath>
            <Output
                TaskParameter="Path"
                PropertyName="SdkPath" />
        </GetFrameworkSdkPath>
        <Message Text="$(SdkPath)"/>
    </Target>
</Project>
```

## <a name="see-also"></a>Viz také

- [Úlohy](../msbuild/msbuild-tasks.md)
- [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)
