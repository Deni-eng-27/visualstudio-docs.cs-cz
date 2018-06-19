---
title: ItemGroup – Element (MSBuild) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#ItemGroup
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- ItemGroup element [MSBuild]
- <ItemGroup> element [MSBuild]
ms.assetid: aac894e3-a9f1-4bbc-a796-6ef07001f35b
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 963c53ed0cd1e74e3e641ac04012e5d0380980fe
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
ms.locfileid: "31569466"
---
# <a name="itemgroup-element-msbuild"></a>ItemGroup – element (MSBuild)
Obsahuje sadu uživatelem definované [položky](../msbuild/item-element-msbuild.md) elementy. Každá položka používán [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] projektu musí být zadány jako podřízená položka `ItemGroup` element.  
  
 \<Project>  
 \<ItemGroup >  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
<ItemGroup Condition="'String A' == 'String B'">  
    <Item1>... </Item1>  
    <Item2>... </Item2>  
</ItemGroup>  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`Condition`|Nepovinný atribut. Podmínku, která má být vyhodnocen. Další informace najdete v tématu [podmínky](../msbuild/msbuild-conditions.md).|  
  
### <a name="child-elements"></a>Podřízené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[Položka](../msbuild/item-element-msbuild.md)|Definuje vstupní hodnoty pro proces sestavení. Může být nula nebo více `Item` elementů v `ItemGroup`.|  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[Projekt](../msbuild/project-element-msbuild.md)|Požadovaný kořenový element [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] souboru projektu.|  
|[cíl](../msbuild/target-element-msbuild.md)|Od verze rozhraní .NET Framework 3.5 `ItemGroup` element může být použito uvnitř `Target` elementu. Další informace najdete v tématu [cíle](../msbuild/msbuild-targets.md).|  
  
## <a name="remarks"></a>Poznámky  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu ukazuje uživatelem definovanou položku kolekce `Res` a `CodeFiles` deklarovaný uvnitř `ItemGroup` elementu. Všechny položky v `Res` položky kolekce obsahuje podřízenou uživatelem definované [itemmetadata –](../msbuild/itemmetadata-element-msbuild.md) elementu.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <ItemGroup>  
        <Res Include = "Strings.fr.resources" >  
            <Culture>fr</Culture>  
        </Res>  
        <Res Include = "Dialogs.fr.resources" >  
            <Culture>fr</Culture>  
        </Res>  
  
        <CodeFiles Include="**\*.cs" Exclude="**\generated\*.cs" />  
        <CodeFiles Include="..\..\Resources\Constants.cs" />  
    </ItemGroup>  
...  
</Project>  
```  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace schématu souboru projektu](../msbuild/msbuild-project-file-schema-reference.md)   
 [Položky](../msbuild/msbuild-items.md)   
 [Společné položky projektu nástroje MSBuild](../msbuild/common-msbuild-project-items.md)