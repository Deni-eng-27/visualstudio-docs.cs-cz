---
title: WizardExtension – Element (šablony sady Visual Studio) | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#WizardExtension
helpviewer_keywords:
- WizardExtension element [Visual Studio Templates]
- <WizardExtension> element [Visual Studio Templates]
ms.assetid: d54b01c1-50f5-4b65-828c-686e2321cc8c
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: c67d85666cc9dd45186b13d9a95ea37eb86447ad
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53963924"
---
# <a name="wizardextension-element-visual-studio-templates"></a>WizardExtension – element (šablony sady Visual Studio)
Obsahuje elementy registrace pro přizpůsobení Průvodce šablonou.  
  
 \<Vstemplate – >  
 ...  
 \<WizardExtension – >  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<WizardExtension>  
    <Assembly>... </Assembly>  
    <FullClassName>... </FullClassName>  
</WizardExtension>  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující oddíly popisují atributy a podřízené a nadřazené elementy.  
  
### <a name="attributes"></a>Atributy  
 Žádné  
  
### <a name="child-elements"></a>Podřízené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[Assembly](../extensibility/assembly-element-visual-studio-template-wizard-extension.md)|Požadovaný element.<br /><br /> Určuje název nebo silný název sestavení, které se zobrazí v globální mezipaměti sestavení. Musí obsahovat alespoň jeden `Assembly` prvek `WizardExtension` elementu.|  
|[FullClassName](../extensibility/fullclassname-element-visual-studio-template-wizard-extension.md)|Požadovaný element.<br /><br /> Plně kvalifikovaný název třídy, která implementuje `IWizard` rozhraní. Musí obsahovat alespoň jeden `FullClassName` prvek `WizardExtension` elementu.|  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[Vstemplate –](../extensibility/vstemplate-element-visual-studio-templates.md)|Obsahuje všechna metadata pro šablony projektu, šablonu položky nebo starter kit.|  
  
## <a name="remarks"></a>Poznámky  
 `WizardExtension` je volitelný podřízený prvek `VSTemplate`.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje metadata pro šablony standardní projektu pro [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] aplikace Windows.  
  
```  
<VSTemplate Version="3.0.0" Type="Item"  
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <Name>MyTemplate</Name>  
        <Description>Template using IWizard extension</Description>  
        <Icon>TemplateIcon.ico</Icon>  
        <ProjectType>CSharp</ProjectType>  
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
    <WizardExtension>  
        <Assembly>MyWizard, Version=1.0.3300.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a, Custom=null</Assembly>  
        <FullClassName>MyWizard.CustomWizard</FullClassName>  
    </WizardExtension>  
</VSTemplate>  
```  
  
## <a name="see-also"></a>Viz také  
 [Odkaz na schéma šablon sady Visual Studio](../extensibility/visual-studio-template-schema-reference.md)   
 [Vytváření šablon projektů a položek](../ide/creating-project-and-item-templates.md)   
 [Postupy: Použití průvodců se šablonami projektů](../extensibility/how-to-use-wizards-with-project-templates.md)