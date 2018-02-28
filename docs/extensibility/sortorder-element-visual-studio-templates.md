---
title: "SortOrder – Element (šablony sady Visual Studio) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#SortOrder
helpviewer_keywords:
- SortOrder element [Visual Studio Templates]
- <SortOrder> element [Visual Studio Templates]
ms.assetid: 151932c1-f08a-4f78-a8d0-bd2f32211a9c
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: a6473e867655974f42f41a276b8becfd12fbab7a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="sortorder-element-visual-studio-templates"></a>SortOrder – element (šablony sady Visual Studio)
Určuje hodnotu, která se používá k uspořádání šablony mezi další šablony ve stejné kategorii, jak se objevuje v buď **nový projekt** nebo **přidat novou položku** dialogové okno.  
  
 \<VSTemplate >  
 \<TemplateData >  
 \<SortOrder >  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<SortOrder> ... </SortOrder>  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
 Žádné  
  
### <a name="child-elements"></a>Podřízené elementy  
 Žádné  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|Požadovaný element.<br /><br /> Rozděluje šablonu a definuje, jak se zobrazuje v buď **nový projekt** nebo **přidat novou položku** dialogové okno.|  
  
## <a name="text-value"></a>Textová hodnota  
 Je vyžadována textová hodnota.  
  
 `integer` Představující hodnotu pořadí řazení.  
  
## <a name="remarks"></a>Poznámky  
 `SortOrder`je volitelný element. Výchozí hodnota je 100 a všechny hodnoty musí být násobky čísla 10.  
  
 `SortOrder` Element je ignorován pro šablony vytvořené uživatelem. Všechny šablony vytvořené uživatelem jsou seřazené podle abecedy.  
  
 Šablony, které mají hodnoty pořadí řazení nízkou se zobrazí buď **nový projekt** nebo **novou položku Přidat** dialogové okno před šablony, které mají vysokou řazení pořadí hodnoty.  
  
## <a name="example"></a>Příklad  
 Následující příklad ilustruje metadata pro standardní [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] šablona třídy.  
  
```  
<VSTemplate Type="Item" Version="3.0.0"  
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <Name>MyClass</Name>  
        <Description>My custom C# class template.</Description>  
        <Icon>Icon.ico</Icon>  
        <ProjectType>CSharp</ProjectType>  
        <SortOrder>290</SortOrder>  
        <DefaultName>MyClass</DefaultName>  
    </TemplateData>  
    <TemplateContent>  
        <ProjectItem>MyClass.cs</ProjectItem>  
    </TemplateContent>  
</VSTemplate>  
```  
  
 V tomto příkladu `SortOrder` element je poměrně vysoké. Je pravděpodobné, aby další [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] bude mít šablon položek `SortOrder` hodnotu nižší, než `290` a zobrazí se před této šablony v **nová položka** dialogové okno.  
  
## <a name="see-also"></a>Viz také  
 [Odkaz na schéma šablon sady Visual Studio](../extensibility/visual-studio-template-schema-reference.md)   
 [Vytváření šablon projektů a položek](../ide/creating-project-and-item-templates.md)