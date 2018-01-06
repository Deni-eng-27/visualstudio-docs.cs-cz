---
title: "Postupy: zobrazení seznamu položek oddělených čárkami | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MSBuild, separating items with semicolons
- MSBuild, formatting item collections
ms.assetid: 3cae844c-7c6d-4144-82dc-efad10ba458f
caps.latest.revision: "12"
author: kempb
ms.author: kempb
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: bc769164187212997b6bc3dcb170c03f7a29ef3b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-display-an-item-list-separated-with-commas"></a>Postupy: Zobrazování seznamu položek oddělených čárkami
Při práci s položkou seznamů v [!INCLUDE[vstecmsbuildengine](../msbuild/includes/vstecmsbuildengine_md.md)] ([!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]), někdy je užitečné k zobrazení obsahu tyto položky seznamů způsobem, který se snadno přečíst. Nebo můžete mít úlohu, která přebírá seznam položek, které jsou odděleny řetězec speciální oddělovače. V obou případech můžete zadat řetězec oddělovač pro seznam položek.  
  
## <a name="separating-items-in-a-list-with-commas"></a>Položky v seznamu oddělíte čárkami  
 Ve výchozím nastavení [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] používá středníky rozdělit položky v seznamu. Představte si třeba `Message` element s následující hodnotou:  
  
 `<Message Text="This is my list of TXT files: @(TXTFile)"/>`  
  
 Když `@(TXTFile)` seznamu položek obsahuje položky App1.txt, App2.txt a App3.txt, zpráva:  
  
 `This is my list of TXT files: App1.txt;App2.txt;App3.txt`  
  
 Pokud chcete změnit výchozí chování, můžete zadat vlastní oddělovač. Syntaxe pro určení oddělovač položka seznamu je:  
  
 `@(ItemListName, '<separator>')`  
  
 Oddělovač může být buď samostatný znak nebo řetězec a musí být uzavřená do jednoduchých uvozovek.  
  
#### <a name="to-insert-a-comma-and-a-space-between-items"></a>Chcete-li vložit čárkou a mezerou mezi položkami  
  
-   Použijte položku zápis podobný následujícímu:  
  
     `@(TXTFile, ', ')`  
  
## <a name="example"></a>Příklad  
 V tomto příkladu [Exec](../msbuild/exec-task.md) úkolů spustí nástroj findstr najít zadané textové řetězce v souboru Phrases.txt. V příkazu findstr literálu řetězce označeny **/c:** přepínače, takže položka oddělovač, `/c:` je vložen mezi položky v `@(Phrase)` seznamu položek.  
  
 V tomto příkladu je ekvivalentní příkazového řádku příkaz:  
  
 `findstr /i /c:hello /c:world /c:msbuild phrases.txt`  
  
```xml  
<Project DefaultTargets = "Find"  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003" >  
  
    <ItemGroup>  
        <Phrase Include="hello"/>  
        <Phrase Include="world"/>  
        <Phrase Include="msbuild"/>  
    </ItemGroup>  
  
    <Target Name = "Find">  
        <!-- Find some strings in a file -->  
        <Exec Command="findstr /i /c:@(Phrase, ' /c:') phrases.txt"/>  
    </Target>  
</Project>  
```  
  
## <a name="see-also"></a>Viz také  
 [MSBuild – Reference](../msbuild/msbuild-reference.md)   
 [Položky](../msbuild/msbuild-items.md)