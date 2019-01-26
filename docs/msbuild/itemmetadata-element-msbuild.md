---
title: Itemmetadata – Element (MSBuild) | Dokumentace Microsoftu
ms.date: 03/13/2017
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
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 78be9b906efd9720d9bc7ccdbe09614899ef6818
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54989585"
---
# <a name="itemmetadata-element-msbuild"></a>Itemmetadata – element (MSBuild)
Obsahuje klíč metadat uživatelem definovanou položku katalogu, který obsahuje hodnotu metadat položky. Položka může mít libovolný počet párů klíč hodnota metadat.  

 \<Project>  
 \<ItemGroup>  
 \<Položka >  

## <a name="syntax"></a>Syntaxe  

```xml  
<ItemMetadataName> Item Metadata value</ItemMetadataName>  
```  

## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  

### <a name="attributes"></a>Atributy  

|Atribut|Popis|  
|---------------|-----------------|  
|`Condition`|Nepovinný atribut.<br /><br /> Podmínku, která má být vyhodnocen. Další informace najdete v tématu [podmínky](../msbuild/msbuild-conditions.md).|  

### <a name="child-elements"></a>Podřízené prvky  
 Žádné  

### <a name="parent-elements"></a>Nadřazené prvky  

|Prvek|Popis|  
|-------------|-----------------|  
|[Položka](../msbuild/item-element-msbuild.md)|Uživatelem definované prvek, který definuje vstupy pro proces sestavení.|  

## <a name="text-value"></a>Textová hodnota  
 Textová hodnota je volitelná.  

 Tento text určuje hodnotu položky metadat, který může být text nebo XML.  

## <a name="example"></a>Příklad  
 Následující příklad kódu ukazuje, jak přidat `Culture` metadata s hodnotou `fr` k položce `CSFile`.  

```xml  
<ItemGroup>  
    <CSFile Include="main.cs" >  
        <Culture>fr</Culture>  
    </CSFile>  
</ItemGroup>  
```  

## <a name="see-also"></a>Viz také:  
 [Referenční dokumentace schématu souboru projektu](../msbuild/msbuild-project-file-schema-reference.md)   
 [Položky](../msbuild/msbuild-items.md)
