---
title: Otherwise – Element (MSBuild) | Dokumentace Microsoftu
ms.date: 03/13/2017
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
ms.openlocfilehash: bb9f6056b83c7701e4d0e5e6eed72bbba1da778d
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53895789"
---
# <a name="otherwise-element-msbuild"></a>Otherwise – element (MSBuild)
Určuje blok kódu budou spuštěny, pokud a pouze tehdy, pokud podmínky všech `When` prvky vyhodnotit `false`.  

 \<Project>  
 \<Zvolte >  
 \<Když >  
 \<Zvolte >  
 ...  
 \<V opačném případě >  
 \<Zvolte >  
 ...  

## <a name="syntax"></a>Syntaxe  

```xml  
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

### <a name="child-elements"></a>Podřízené prvky  

|Prvek|Popis|  
|-------------|-----------------|  
|[Zvolte](../msbuild/choose-element-msbuild.md)|Volitelný element.<br /><br /> Vyhodnotí jako podřízené prvky a vyberte jednu část kódu ke spuštění. Může být nula nebo více `Choose` prvky `Otherwise` elementu.|  
|[ItemGroup](../msbuild/itemgroup-element-msbuild.md)|Volitelný element.<br /><br /> Obsahuje sadu uživatelem definované [položky](../msbuild/item-element-msbuild.md) elementy. Může být nula nebo více `ItemGroup` prvky `Otherwise` elementu.|  
|[PropertyGroup](../msbuild/propertygroup-element-msbuild.md)|Volitelný element.<br /><br /> Obsahuje sadu uživatelem definované [vlastnost](../msbuild/property-element-msbuild.md) elementy. Může být nula nebo více `PropertyGroup` prvky `Otherwise` elementu.|  

### <a name="parent-elements"></a>Nadřazené prvky  

|Prvek|Popis|  
|-------------|-----------------|  
|[Zvolte](../msbuild/choose-element-msbuild.md)|Vyhodnotí jako podřízené prvky a vyberte jednu část kódu ke spuštění.|  

## <a name="remarks"></a>Poznámky  
 Může existovat pouze jeden `Otherwise` prvek `Choose` element a musí být posledním prvkem.  

 `Choose`, `When`, A `Otherwise` elementy se používají společně poskytují způsob, jak vybrat jednu část kódu k provedení počet možných alternativy. Další informace najdete v tématu [podmíněné konstrukce](../msbuild/msbuild-conditional-constructs.md).  

## <a name="example"></a>Příklad  
 Následující projekt používá `Choose` které sadu hodnot vlastností v vybrat element `When` prvky pro nastavení. Pokud `Condition` atributy obou `When` prvky vyhodnotit `false`, vlastnost hodnoty v `Otherwise` element jsou nastavené.  

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

## <a name="see-also"></a>Viz také:  
 [Podmíněné konstrukce](../msbuild/msbuild-conditional-constructs.md)   
 [Referenční dokumentace schématu souboru projektu](../msbuild/msbuild-project-file-schema-reference.md)
