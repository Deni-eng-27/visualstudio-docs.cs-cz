---
title: Otherwise – Element (MSBuild) | Microsoft Docs
ms.custom: ''
ms.date: 03/13/2017
ms.technology: msbuild
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#Otherwise
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- <Otherwise> Element [MSBuild]
- Otherwise Element [MSBuild]
ms.assetid: de3997e9-1595-4263-a886-95530b56a319
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d018b26f2df32b9e3cc1e3fae65ec8b3d3394806
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
ms.locfileid: "31570077"
---
# <a name="otherwise-element-msbuild"></a>Otherwise – element (MSBuild)
Určuje blok kódu provést pokud a pouze v případě podmínky všech `When` elementy vyhodnocení `false`.  

 \<Project>  
 \<Zvolte >  
 \<Když >  
 \<Zvolte >  
 ...  
 \<V opačném případě >  
 \<Zvolte >  
 ...  

## <a name="syntax"></a>Syntaxe  

```  
<Otherwise>  
    <PropertyGroup>... </PropertyGroup>  
    <ItemGroup>... </ItemGroup>  
    <Choose>... </Choose>  
</Otherwise>  
```  

## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  

### <a name="attributes"></a>Atributy  
 Žádné  

### <a name="child-elements"></a>Podřízené elementy  

|Prvek|Popis|  
|-------------|-----------------|  
|[Zvolte](../msbuild/choose-element-msbuild.md)|Volitelný element.<br /><br /> Vyhodnotí podřízené elementy a vyberte jeden oddíl vykonání kódu. Může být nula nebo více `Choose` elementů v `Otherwise` elementu.|  
|[ItemGroup](../msbuild/itemgroup-element-msbuild.md)|Volitelný element.<br /><br /> Obsahuje sadu uživatelem definované [položky](../msbuild/item-element-msbuild.md) elementy. Může být nula nebo více `ItemGroup` elementů v `Otherwise` elementu.|  
|[PropertyGroup –](../msbuild/propertygroup-element-msbuild.md)|Volitelný element.<br /><br /> Obsahuje sadu uživatelem definované [vlastnost](../msbuild/property-element-msbuild.md) elementy. Může být nula nebo více `PropertyGroup` elementů v `Otherwise` elementu.|  

### <a name="parent-elements"></a>Nadřazené elementy  

|Prvek|Popis|  
|-------------|-----------------|  
|[Zvolte](../msbuild/choose-element-msbuild.md)|Vyhodnotí podřízené elementy a vyberte jeden oddíl vykonání kódu.|  

## <a name="remarks"></a>Poznámky  
 Může být jen jeden `Otherwise` element v `Choose` element a musí být posledním prvkem.  

 `Choose`, `When`, A `Otherwise` prvky se společně používají k poskytnout způsob, jak vybrat jeden oddíl vykonání mezi několika možných alternativních kódu. Další informace najdete v tématu [podmíněné konstrukce](../msbuild/msbuild-conditional-constructs.md).  

## <a name="example"></a>Příklad  
 Následující projektu používá `Choose` které sadu hodnot vlastností v vybrat element `When` elementy nastavit. Pokud `Condition` atributy i `When` elementy vyhodnocení `false`, vlastnost hodnoty ve `Otherwise` element jsou nastavené.  

```xml  
<Project  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003" >  
    <PropertyGroup>  
        <Configuration Condition="'$(Configuration)' == ''">Debug</Configuration>  
        <OutputType>Exe</OutputType>  
        <RootNamespace>ConsoleApplication1</RootNamespace>  
        <AssemblyName>ConsoleApplication1</AssemblyName>  
        <WarningLevel>4</WarningLevel>  
    </PropertyGroup>  
    <Choose>  
        <When Condition=" '$(Configuration)'=='debug' ">  
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
        <Otherwise>  
            <PropertyGroup>  
                <DebugSymbols>true</DebugSymbols>  
                <Optimize>false</Optimize>  
                <OutputPath>.\bin\$(Configuration)\</OutputPath>  
                <DefineConstants>DEBUG;TRACE</DefineConstants>  
            </PropertyGroup>  
        </Otherwise>  
        </Choose>  
    <Import Project="$(MSBuildBinPath)\Microsoft.CSharp.targets" />  
</Project>  
```  

## <a name="see-also"></a>Viz také  
 [Podmíněné konstrukce](../msbuild/msbuild-conditional-constructs.md)   
 [Referenční dokumentace schématu souboru projektu](../msbuild/msbuild-project-file-schema-reference.md)
