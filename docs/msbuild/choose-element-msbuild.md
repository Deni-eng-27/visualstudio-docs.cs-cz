---
title: "Choose – prvek (MSBuild) | Microsoft Docs"
ms.custom: 
ms.date: 03/13/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/developer/msbuild/2003#Choose
dev_langs:
- VB
- CSharp
- C++
- jsharp
- xml
helpviewer_keywords:
- <Choose> Element [MSBuild]
- Choose Element [MSBuild]
ms.assetid: 7b8b025a-d944-4f5c-9018-c89fc2ef146d
caps.latest.revision: "8"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: e199dbfc171688cd0970cf340aef0dfd3584155a
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="choose-element-msbuild"></a>Choose – element (MSBuild)
Vyhodnotí podřízené elementy a vyberte jednu sadu `ItemGroup` elementy nebo `PropertyGroup` elementy k vyhodnocení.  

 \<Projekt >  
 \<Zvolte >  
 \<Když >  
 \<Zvolte >  
 ...  
 \<V opačném případě >  
 \<Zvolte >  
 ...  

## <a name="syntax"></a>Syntaxe  

```  
<Choose>  
    <When Condition="'StringA'=='StringB'">... </When>  
    <Otherwise>... </Otherwise>  
</Choose>  
```  

## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  

### <a name="attributes"></a>Atributy  
 Žádné  

### <a name="child-elements"></a>Podřízené elementy  

|Prvek|Popis|  
|-------------|-----------------|  
|[V opačném případě](../msbuild/otherwise-element-msbuild.md)|Volitelný element.<br /><br /> Určuje blok kódu `PropertyGroup` a `ItemGroup` elementy k vyhodnocení, jestli podmínky všech `When` elementy vyhodnocení `false`. Může být nula nebo jeden `Otherwise` elementů v `Choose` element a musí být posledním prvkem.|  
|[Kdy](../msbuild/when-element-msbuild.md)|Požadovaný element.<br /><br /> Určuje možné blok kódu pro `Choose` elementu, který chcete vybrat. Může být jeden nebo více `When` elementů v `Choose` elementu.|  

### <a name="parent-elements"></a>Nadřazené elementy  

|Prvek|Popis|  
|-------------|-----------------|  
|[V opačném případě](../msbuild/otherwise-element-msbuild.md)|Určuje blok kódu provést, pokud všechny podmínky `When` elementy vyhodnocení `false`.|  
|[Projekt](../msbuild/project-element-msbuild.md)|Požadovaný kořenový element [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] souboru projektu.|  
|[Kdy](../msbuild/when-element-msbuild.md)|Určuje možné blok kódu pro `Choose` elementu, který chcete vybrat.|  

## <a name="remarks"></a>Poznámky  
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
