---
title: Výstup – Element (MSBuild) | Microsoft Docs
ms.custom: ''
ms.date: 03/13/2017
ms.technology: msbuild
ms.topic: conceptual
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#Output
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- <Output> Element [MSBuild]
- Output Element [MSBuild]
ms.assetid: 34bc7cd1-efd3-4b57-b691-4584eeb6a0e9
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 59d5352bb2ed3eb7e5e79eacb2c2e0e55a9aad20
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="output-element-msbuild"></a>Output – element (MSBuild)
Úložiště úlohy výstupní hodnoty položky a vlastnosti.  

 \<Project>  
 \<Cíl >  
 \<Úlohy >  
 \<Výstup >  

## <a name="syntax"></a>Syntaxe  

```  
<Output TaskParameter="Parameter"  
    PropertyName="PropertyName"   
    Condition = "'String A' == 'String B'" />  
```  

## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  

### <a name="attributes"></a>Atributy  

|Atribut|Popis|  
|---------------|-----------------|  
|`TaskParameter`|Požadovaný atribut.<br /><br /> Název úlohy je výstupní parametr.|  
|`PropertyName`|Buď `PropertyName` nebo `ItemName` atribut je požadován.<br /><br /> Vlastnost, která přijímá úlohu výstupu hodnotu parametru. Projekt pak můžete odkazovat vlastnost s `$(` *PropertyName* `)` syntaxe. Název této vlastnosti může být buď nový název vlastnosti nebo název, který je již definován v projektu.<br /><br /> Tento atribut nelze použít, pokud `ItemName` se také používá.|  
|`ItemName`|Buď `PropertyName` nebo `ItemName` atribut je požadován.<br /><br /> Položka, která přijímá úlohu výstupu hodnotu parametru. Projekt pak můžete odkazovat položka se `@(` *název položky* `)` syntaxe. Název položky může být buď nový název položky nebo název, který je již definován v projektu.<br /><br /> Tento atribut nelze použít, pokud `PropertyName` se také používá.|  
|`Condition`|Nepovinný atribut.<br /><br /> Podmínku, která má být vyhodnocen. Další informace najdete v tématu [podmínky](../msbuild/msbuild-conditions.md).|  

### <a name="child-elements"></a>Podřízené elementy  
 Žádné  

### <a name="parent-elements"></a>Nadřazené elementy  

|Prvek|Popis|  
|-------------|-----------------|  
|[Úloha](../msbuild/task-element-msbuild.md)|Vytvoří a spustí instanci [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] úloh.|  

## <a name="example"></a>Příklad  
 Následující příklad kódu ukazuje `Csc` úloh se spouští uvnitř `Target` elementu. Mimo rámec tohoto příkladu jsou deklarovány položky a vlastnosti předaný parametry úlohy. Hodnota z výstupního parametru `OutputAssembly` je uložen v `FinalAssemblyName` položky a hodnotu z výstupního parametru `BuildSucceeded` je uložen v `BuildWorked` vlastnost. Další informace najdete v tématu [úlohy](../msbuild/msbuild-tasks.md).  

```xml  
<Target Name="Compile" DependsOnTargets="Resources">  
    <Csc  Sources="@(CSFile)"  
            TargetType="library"  
            Resources="@(CompiledResources)"  
            EmitDebugInformation="$(includeDebugInformation)"  
            References="@(Reference)"  
            DebugType="$(debuggingType)"  
            OutputAssembly="$(builtdir)\$(MSBuildProjectName).dll" >  
        <Output TaskParameter="OutputAssembly"  
                  ItemName="FinalAssemblyName" />  
        <Output TaskParameter="BuildSucceeded"  
                  PropertyName="BuildWorked" />  
    </Csc>  
</Target>  
```  

## <a name="see-also"></a>Viz také  
 [Referenční dokumentace schématu souboru projektu](../msbuild/msbuild-project-file-schema-reference.md)   
 [Úlohy](../msbuild/msbuild-tasks.md)
