---
title: 'Postupy: použití vyhrazených znaků XML v souborech projektu | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- MSBuild, using reserved XML characters
- MSBuild, reserved XML characters
ms.assetid: 1ae37275-96bf-4e6e-897b-6b048e5bbe93
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a041802af1c2fe8cfa195990e6eda3e9b49d773a
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "77633769"
---
# <a name="how-to-use-reserved-xml-characters-in-project-files"></a>Postupy: použití vyhrazených znaků XML v souborech projektu

Při vytváření souborů projektu může být nutné použít vyhrazené znaky XML, například v hodnotách vlastností nebo v hodnotách parametrů úkolu. Některé vyhrazené znaky však musí být nahrazeny pojmenovanou entitou, aby bylo možné analyzovat soubor projektu.

## <a name="use-reserved-characters"></a>Použít vyhrazené znaky

 V následující tabulce jsou popsány vyhrazené znaky XML, které musí být nahrazeny odpovídající pojmenované entitou, aby bylo možné analyzovat soubor projektu.

|Vyhrazený znak|Pojmenovaná entita|
|------------------------|------------------|
|\<|&amp;lt|
|>|&amp;gt|
|&|&amp;webové|
|"|&amp;quot;|
|'|&amp;{0}|

#### <a name="to-use-double-quotes-in-a-project-file"></a>Použití dvojitých uvozovek v souboru projektu

- Nahraďte dvojité uvozovky odpovídající pojmenovanou entitou &amp; quot;. Chcete-li například umístit dvojité uvozovky kolem `EXEFile` seznamu položek, zadejte:

    ```xml
    <Message Text="The output file is &quot;@(EXEFile)&quot;."/>
    ```

## <a name="example"></a>Příklad

 V následujícím příkladu kódu se pomocí dvojitých uvozovek zvýrazní název souboru ve zprávě, která je výstupem souboru projektu.

```xml
<Project DefaultTargets="Compile"
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003" >
    <!-- Set the application name as a property -->
    <PropertyGroup>
        <appname>"HelloWorldCS"</appname>
    </PropertyGroup>
    <!-- Specify the inputs -->
    <ItemGroup>
        <CSFile Include = "consolehwcs1.cs" />
    </ItemGroup>
    <Target Name = "Compile">
        <!-- Run the Visual C# compilation using input
        files of type CSFile -->
        <Csc Sources = "@(CSFile)">
            <!-- Set the OutputAssembly attribute of the CSC task
            to the name of the executable file that is created -->
            <Output
                TaskParameter = "OutputAssembly"
                ItemName = "EXEFile"/>
        </Csc>
        <!-- Log the file name of the output file -->
        <Message Text="The output file is &quot;@(EXEFile)&quot;."/>
    </Target>
</Project>
```

## <a name="see-also"></a>Viz také

- [Referenční dokumentace nástroje MSBuild](../msbuild/msbuild-reference.md)
- [Nástroji](../msbuild/msbuild.md)
