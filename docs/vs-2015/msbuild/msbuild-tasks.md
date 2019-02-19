---
title: Úlohy nástroje MSBuild | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: msbuild
ms.topic: reference
helpviewer_keywords:
- tasks
- MSBuild, tasks
ms.assetid: 5d3cc4a7-e5db-4f73-b707-8b6882fddcf8
caps.latest.revision: 21
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 611bc5c0fbb81d38aa10561d8603ef281a51d9a1
ms.sourcegitcommit: a83c60bb00bf95e6bea037f0e1b9696c64deda3c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/19/2019
ms.locfileid: "54788686"
---
# <a name="msbuild-tasks"></a>Úlohy nástroje MSBuild
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
Platformy sestavení musí být schopné spustit libovolný počet akcí během procesu sestavení. [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] používá *úlohy* k provedení těchto akcí. Úkol je jednotka spustitelný kód, který používá [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] k operacím atomického sestavení.  
  
## <a name="task-logic"></a>Úloha logiky  
 [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] Formát souboru projektu XML nelze spustit plně sestavení operací na sama, takže logiku úkolu musí být implementované mimo rámec souborů projektu.  
  
 Logika spuštění úkolu je implementován jako třída rozhraní .NET, která implementuje <xref:Microsoft.Build.Framework.ITask> rozhraní, která je definována v <xref:Microsoft.Build.Framework> oboru názvů.  
  
 Třída úloha také definuje vstupní a výstupní parametry k dispozici úkolu v souboru projektu. Všechny veřejné nastavitelné nestatické neabstraktní vlastností vystavovaných třídami třída úlohy je přístupný v souboru projektu tak, že na odpovídající atribut se stejným názvem [úloh](../msbuild/task-element-msbuild.md) elementu.  
  
 Můžete napsat vlastní úkol vytvořením spravovaného třídu, která implementuje <xref:Microsoft.Build.Framework.ITask> rozhraní. Další informace najdete v tématu [zápis úloh](../msbuild/task-writing.md).  
  
## <a name="executing-a-task-from-a-project-file"></a>Spuštění úlohy ze souboru projektu  
 Před spuštěním úkolu v souboru projektu, je třeba nejprve namapovat typ v sestavení, který implementuje úkolů s názvem úkolu [UsingTask](../msbuild/usingtask-element-msbuild.md) elementu. Díky tomu [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] věděli, kde hledat logika spuštění úkolu, pokud se najde v souboru projektu.  
  
 Spustit úlohu v [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] souboru projektu, vytvořte prvek se název úkolu jako podřízený objekt `Target` elementu. Pokud úloha přijímá parametry, ty jsou předány jako atributy elementu.  
  
 [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] Položka vlastnosti a seznamy se dá použít jako parametry. Například následující kód volá `MakeDir` úloh a nastaví hodnotu vlastnosti `Directories` vlastnost `MakeDir` rovna hodnotě tohoto objektu `BuildDir` vlastnosti deklarované v předchozím příkladu.  
  
```  
<Target Name="MakeBuildDirectory">  
    <MakeDir  
        Directories="$(BuildDir)" />  
</Target>  
```  
  
 Úlohy může také vracet informace do souboru projektu, která mohou být uložena v položky nebo vlastnosti pro pozdější použití. Například následující kód volá `Copy` úlohy a ukládá informace od `CopiedFiles` výstupní vlastnosti `SuccessfullyCopiedFiles` seznam položek.  
  
```  
<Target Name="CopyFiles">  
    <Copy  
        SourceFiles="@(MySourceFiles)"  
        DestinationFolder="@(MyDestFolder)">  
        <Output  
            TaskParameter="CopiedFiles"  
            ItemName="SuccessfullyCopiedFiles"/>  
     </Copy>  
</Target>  
```  
  
## <a name="included-tasks"></a>Součástí úlohy  
 [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] se dodává s mnoha úkoly, jako [kopírování](../msbuild/copy-task.md), který zkopíruje soubory, [MakeDir](../msbuild/makedir-task.md), vytvoření adresářů a [Csc](../msbuild/csc-task.md), který zkompiluje [!INCLUDE[csprcs](../includes/csprcs-md.md)] souborů zdrojového kódu. Úplný seznam dostupných úkolů a informace o použití najdete v části [– referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md).  
  
## <a name="overridden-tasks"></a>Přepsané úlohy  
 [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] vyhledá pro úlohy v několika umístěních. První místo nachází soubory s příponou. OverrideTasks uložené v adresáři rozhraní .NET Framework. Úkoly v těchto souborech přepsat všechny úkoly se stejnými názvy, včetně úkolů v souboru projektu. Druhé místo je v souborech s příponou. Úkoly v adresáři rozhraní .NET Framework. Pokud úkol nebyl nalezen v některém z těchto umístění, použije se úkolu v souboru projektu.  
  
## <a name="see-also"></a>Viz také  
 [Koncepty nástroje MSBuild](../msbuild/msbuild-concepts.md)   
 [MSBuild](msbuild.md)   
 [Zápis úloh](../msbuild/task-writing.md)   
 [Vložené úlohy](../msbuild/msbuild-inline-tasks.md)
