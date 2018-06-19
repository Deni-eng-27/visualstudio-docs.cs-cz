---
title: Itemmetadata – Element (MSBuild) | Microsoft Docs
ms.custom: ''
ms.date: 03/13/2017
ms.technology: msbuild
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- ItemMetadata Element [MSBuild]
- <ItemMetadata> Element [MSBuild]
ms.assetid: e3db5122-202d-43a9-b2f4-3e0ec4ed3d08
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2e3251f3f4f9ee43584d427ada7c014a566dc4db
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
ms.locfileid: "31567977"
---
# <a name="itemmetadata-element-msbuild"></a>ItemMetadata – element (MSBuild)
Obsahuje klíč metadata uživatelem definovanou položku, který obsahuje hodnotu položky metadat. Položka může mít libovolný počet páry klíč hodnota metadat.  

 \<Project>  
 \<ItemGroup >  
 \<Položka >  

## <a name="syntax"></a>Syntaxe  

```  
<ItemMetadataName> Item Metadata value</ItemMetadataName>  
```  

## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  

### <a name="attributes"></a>Atributy  

|Atribut|Popis|  
|---------------|-----------------|  
|`Condition`|Nepovinný atribut.<br /><br /> Podmínku, která má být vyhodnocen. Další informace najdete v tématu [podmínky](../msbuild/msbuild-conditions.md).|  

### <a name="child-elements"></a>Podřízené elementy  
 Žádné  

### <a name="parent-elements"></a>Nadřazené elementy  

|Prvek|Popis|  
|-------------|-----------------|  
|[Položka](../msbuild/item-element-msbuild.md)|Element definovaný uživatelem, který definuje vstupy pro proces sestavení.|  

## <a name="text-value"></a>Textová hodnota  
 Textová hodnota je volitelná.  

 Tento text určuje hodnota metadata položky, které může být text nebo XML.  

## <a name="remarks"></a>Poznámky  

## <a name="example"></a>Příklad  
 Následující příklad kódu ukazuje, jak přidat `Culture` metadata s hodnotou `fr` k položce `CSFile`.  

```xml  
<ItemGroup>  
    <CSFile Include="main.cs" >  
        <Culture>fr</Culture>  
    </CSFile>  
</ItemGroup>  
```  

## <a name="see-also"></a>Viz také  
 [Referenční dokumentace schématu souboru projektu](../msbuild/msbuild-project-file-schema-reference.md)   
 [Položky](../msbuild/msbuild-items.md)
