---
title: ProjectSubType – Element (šablony sady Visual Studio) | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#ProjectSubType
helpviewer_keywords:
- ProjectSubType element [Visual Studio Templates]
- <ProjectSubType> element [Visual Studio Templates]
ms.assetid: f6895cd4-3e95-4f0e-aa9e-8c7750f46ed4
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 069c5f96cd2e8e5e4280800a6b39c7cf87936aaf
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54955435"
---
# <a name="projectsubtype-element-visual-studio-templates"></a>ProjectSubType – element (šablony sady Visual Studio)
Klasifikuje v subcategory hodnoty zadané v šabloně `ProjectType` elementu.  
  
 \<Vstemplate – >  
 \<TemplateData>  
 \<ProjectSubType>  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
<ProjectSubType> SubType </ProjectSubType>  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující oddíly popisují atributy a podřízené a nadřazené elementy.  
  
### <a name="attributes"></a>Atributy  
 Žádné  
  
### <a name="child-elements"></a>Podřízené prvky  
 Žádné  
  
### <a name="parent-elements"></a>Nadřazené prvky  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|Požadovaný element.<br /><br /> Rozděluje šablonu a definuje, jak se zobrazuje **nový projekt** nebo **přidat novou položku** dialogové okno.|  
  
## <a name="text-value"></a>Textová hodnota  
 Je vyžadována textová hodnota.  
  
 Tato hodnota určuje subcategory šablony.  
  
## <a name="remarks"></a>Poznámky  
 `ProjectSubType` je volitelný podřízený prvek `TemplateData`.  
  
 `ProjectSubType` Element poskytuje podkategorii tak, aby [ProjectType](../extensibility/projecttype-element-visual-studio-templates.md) elementu. Tato hodnota může obsahovat:  
  
- `SmartDevice-NETCFv1`: Určuje, že šablona cílí [!INCLUDE[Compact](../extensibility/includes/compact_md.md)] verze 1.0.  
  
- `SmartDevice-NETCFv2`: Určuje, že šablona cílí [!INCLUDE[Compact](../extensibility/includes/compact_md.md)] verze 2.0.  
  
  Pokud šablona obsahuje `ProjectType` element s hodnotou `Web`, `ProjectSubType` prvek určuje programovací jazyk šablony. Tento prvek může mít následující hodnoty:  
  
- `CSharp`: Určuje, že šablona vytváří [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] webový projekt nebo položku.  
  
- `VisualBasic`: Určuje, že šablona vytváří [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] webový projekt nebo položku.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje metadata pro šablona projektu pro [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] cílení aplikace zařízení [!INCLUDE[Compact](../extensibility/includes/compact_md.md)] verze 2.0.  
  
```  
<VSTemplate Type="Project" Version="3.0.0"  
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <Name>My template</Name>  
        <Description>A basic device template</Description>  
        <Icon>TemplateIcon.ico</Icon>  
        <ProjectType>CSharp</ProjectType>  
        <ProjectSubType>SmartDevice-NETCFv2</ProjectSubType>  
    </TemplateData>  
    <TemplateContent>  
        <Project File="MyTemplate.csproj">  
            <ProjectItem>Form1.cs<ProjectItem>  
            <ProjectItem>Form1.Designer.cs</ProjectItem>  
            <ProjectItem>Program.cs</ProjectItem>  
            <ProjectItem>Properties\AssemblyInfo.cs</ProjectItem>  
            <ProjectItem>Properties\Resources.resx</ProjectItem>  
            <ProjectItem>Properties\Resources.Designer.cs</ProjectItem>  
            <ProjectItem>Properties\Settings.settings</ProjectItem>  
            <ProjectItem>Properties\Settings.Designer.cs</ProjectItem>  
        </Project>  
    </TemplateContent>  
</VSTemplate>  
```  
  
## <a name="see-also"></a>Viz také:  
 [Visual Studio odkaz na schéma šablon](../extensibility/visual-studio-template-schema-reference.md)   
 [Vytváření šablon projektů a položek](../ide/creating-project-and-item-templates.md)   
 [ProjectType – element (šablony sady Visual Studio)](../extensibility/projecttype-element-visual-studio-templates.md)