---
title: "Úloha – Element (MSBuild) | Microsoft Docs"
ms.custom: 
ms.date: 03/13/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- Task element [MSBuild]
- <Task> element [MSBuild]
ms.assetid: d82e2485-e5f0-4936-a357-745bacccc299
caps.latest.revision: "22"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: 6e2aab5959a27807e44270c55c77b7d6d9229f18
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="task-element-msbuild"></a>Task – element (MSBuild)
Vytvoří a spustí instanci [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] úloh. Název elementu je určen podle názvu úlohy vytváří.  

 \<Projekt >  
 \<Cíl >  

## <a name="syntax"></a>Syntaxe  

```  
<Task Parameter1="Value1"... ParameterN="ValueN"  
    ContinueOnError="WarnAndContinue/true/ErrorAndContinue/ErrorAndStop/false"  
    Condition="'String A' == 'String B'" >  
    <Output... />  
</Task>  
```  

## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  

### <a name="attributes"></a>Atributy  

|Atribut|Popis|  
|---------------|-----------------|  
|`Condition`|Nepovinný atribut. Podmínku, která má být vyhodnocen. Další informace najdete v tématu [podmínky](../msbuild/msbuild-conditions.md).|  
|`ContinueOnError`|Nepovinný atribut. Může obsahovat jednu z následujících hodnot:<br /><br /> -   **WarnAndContinue** nebo **true**. Pokud úloha selže, úlohy v [cíl](../msbuild/target-element-msbuild.md) elementu a sestavení dále provést, a všechny chyby z úlohy se považují za upozornění.<br />-   **ErrorAndContinue**. Pokud úloha selže, úlohy v `Target` elementu a sestavení dále provést, a všechny chyby z úlohy se považují za chyby.<br />-   **ErrorAndStop** nebo **false** (výchozí). Pokud úloha selže, ve zbývajících úkolech v `Target` elementu a sestavení nebudou provedeny a celý `Target` elementu a sestavení považován za neúspěšný.<br /><br /> Verze rozhraní .NET Framework před 4.5 podporovaná jenom `true` a `false` hodnoty.<br /><br /> Další informace najdete v tématu [postupy: ignorování chyb v úlohách](../msbuild/how-to-ignore-errors-in-tasks.md).|  
|`Parameter`|Vyžaduje, pokud třída úlohy obsahuje jeden nebo více vlastností označený verzí `[Required]` atribut.<br /><br /> Uživatelem definované úloh parametr, který obsahuje hodnotu parametru jako jeho hodnotu. Může být libovolný počet parametrů `Task` element s každý atribut je namapovaný na vlastnost .NET ve třídě úloh.|  

### <a name="child-elements"></a>Podřízené elementy  

|Prvek|Popis|  
|-------------|-----------------|  
|[Výstup](../msbuild/output-element-msbuild.md)|Úložiště výstupu z úlohy v souboru projektu. Může být nula nebo více `Output` elementy v úloze.|  

### <a name="parent-elements"></a>Nadřazené elementy  

|Prvek|Popis|  
|-------------|-----------------|  
|[Cíl](../msbuild/target-element-msbuild.md)|Element kontejneru pro [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] úlohy.|  

## <a name="remarks"></a>Poznámky  
 A `Task` element v [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] souboru projektu vytvoří instance úlohy, nastaví vlastnosti a provede ji. `Output` Element uloží výstupní parametry ve vlastnostech nebo položky, které mají být použity jinde v souboru projektu.  

 Pokud jsou k dispozici [OnError](../msbuild/onerror-element-msbuild.md) elementů v nadřazené `Target` element úlohy, se budou vyhodnocovat pořád Pokud se úloha nezdaří a `ContinueOnError` má hodnotu `false`. Další informace o úlohách najdete v tématu [úlohy](../msbuild/msbuild-tasks.md).  

## <a name="example"></a>Příklad  
 Následující příklad kódu vytvoří instanci [Csc – úloha](../msbuild/csc-task.md) třídu, nastaví šest vlastností a provede úlohu. Po spuštění, hodnota `OutputAssembly` vlastnosti objektu se nachází v seznamu položek s názvem `FinalAssemblyName`.  

```xml  
<Target Name="Compile" DependsOnTarget="Resources" >  
    <Csc Sources="@(CSFile)"  
          TargetType="library"  
          Resources="@(CompiledResources)"  
          EmitDebugInformation="$(includeDebugInformation)"  
          References="@(Reference)"  
          DebugType="$(debuggingType)" >  
        <Output TaskParameter="OutputAssembly"  
                  ItemName="FinalAssemblyName" />  
    </Csc>  
</Target>  
```  

## <a name="see-also"></a>Viz také  
 [Úlohy](../msbuild/msbuild-tasks.md)   
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)   
 [Referenční dokumentace schématu souboru projektu](../msbuild/msbuild-project-file-schema-reference.md)
