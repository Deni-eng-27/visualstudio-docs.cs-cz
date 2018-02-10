---
title: "Podmíněné konstrukty nástroje MSBuild | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- <Choose> Element [MSBuild]
- Choose Element [MSBuild]
- conditional constructs [MSBuild]
- MSBuild, conditional constructs
- <When> Element [MSBuild]
- <Otherwise> Element [MSBuild]
- Otherwise Element [MSBuild]
- When Element [MSBuild]
ms.assetid: dd54258e-f4fb-448f-9da4-d1817e0cbaf2
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: f018ec733248f6663e2cf2292599df9d2afdc81c
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/09/2018
---
# <a name="msbuild-conditional-constructs"></a>Podmíněné konstrukty nástroje MSBuild
[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] poskytuje mechanismus pro buď / nebo zpracování s [zvolte](../msbuild/choose-element-msbuild.md), [při](../msbuild/when-element-msbuild.md), a [jinak](../msbuild/otherwise-element-msbuild.md) elementy.  
  
## <a name="using-the-choose-element"></a>Pomocí Choose – prvek  
 `Choose` Element obsahuje řadu `When` prvky s `Condition` atributy, které jsou testovány v pořadí od shora dolů, dokud nebude vyhodnocen jako jeden `true`. Pokud více než jeden `When` vyhodnocen jako element `true`, je použita pouze první z nich. `Otherwise` Elementu, pokud existuje, budou vyhodnoceny, pokud žádná podmínka na `When` vyhodnocen jako element `true`.  
  
 `Choose`elementy lze použít jako podřízených elementů `Project`, `When` a `Otherwise` elementy. `When`a `Otherwise` může mít elementy `ItemGroup`, `PropertyGroup`, nebo `Choose` podřízené elementy.  
  
## <a name="example"></a>Příklad  
 Následující příklad používá `Choose` a `When` prvky pro buď / nebo zpracování. V závislosti na hodnotě jsou nastavené vlastnosti a položek pro projekt `Configuration` vlastnost.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003" >  
    <PropertyGroup>  
        <Configuration Condition=" '$(Configuration)' == '' ">Debug</Configuration>  
        <OutputType>Exe</OutputType>  
        <RootNamespace>ConsoleApplication1</RootNamespace>  
        <AssemblyName>ConsoleApplication1</AssemblyName>  
        <WarningLevel>4</WarningLevel>  
    </PropertyGroup>  
    <Choose>  
        <When Condition=" '$(Configuration)'=='Debug' ">  
            <PropertyGroup>  
                <DebugSymbols>true</DebugSymbols>  
                <DebugType>full</DebugType>  
                <Optimize>false</Optimize>  
                <OutputPath>.\bin\Debug\</OutputPath>  
                <DefineConstants>DEBUG;TRACE</DefineConstants>  
            </PropertyGroup>  
            <ItemGroup>  
                <Compile Include="UnitTesting\*.cs" />  
                <Reference Include="NUnit.dll" />  
            </ItemGroup>  
        </When>  
        <When Condition=" '$(Configuration)'=='retail' ">  
            <PropertyGroup>  
                <DebugSymbols>false</DebugSymbols>  
                <Optimize>true</Optimize>  
                <OutputPath>.\bin\Release\</OutputPath>  
                <DefineConstants>TRACE</DefineConstants>  
            </PropertyGroup>  
        </When>  
    </Choose>  
    <!-- Rest of Project -->  
</Project>  
```  
  
## <a name="see-also"></a>Viz také  
 [Choose – prvek (MSBuild)](../msbuild/choose-element-msbuild.md)   
 [Když – Element (MSBuild)](../msbuild/when-element-msbuild.md)   
 [Otherwise – Element (MSBuild)](../msbuild/otherwise-element-msbuild.md)   
 [Referenční dokumentace nástroje MSBuild](../msbuild/msbuild-reference.md)