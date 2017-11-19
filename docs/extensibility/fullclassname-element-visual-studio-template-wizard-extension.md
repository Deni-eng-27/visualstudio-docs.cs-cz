---
title: "Fullclassname – Element (rozšíření Průvodce pro šablony sady Visual Studio) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/developer/vstemplate/2005#FullClassName
helpviewer_keywords: FullClassName element [Visual Studio project template]
ms.assetid: 651e1010-d529-4856-85ff-c77ceca5d2ed
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: a94a6d95bee32da52d484bc4203433b092ef2b82
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="fullclassname-element-visual-studio-template-wizard-extension"></a>FullClassName – element (rozšíření průvodce pro šablony sady Visual Studio)
Plně kvalifikovaný název třídy, která implementuje `IWizard` rozhraní.  
  
 \<VSTemplate >  
 \<WizardExtension >  
 ...  
 \<Fullclassname – >  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<FullClassName>ClassName</FullClassName>  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující oddíly popisují atributy a podřízené a nadřazené elementy.  
  
### <a name="attributes"></a>Atributy  
 Žádné  
  
### <a name="child-elements"></a>Podřízené elementy  
 Žádné  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[WizardExtension](../extensibility/wizardextension-element-visual-studio-templates.md)|Obsahuje prvky registrace pro přizpůsobení Průvodce šablonou.|  
  
## <a name="text-value"></a>Textová hodnota  
 Je vyžadována textová hodnota.  
  
 Tento text určuje třídu, která implementuje `IWizard` rozhraní. Pro zadanou třídu, musí existovat v sestavení určeného [sestavení](../extensibility/assembly-element-visual-studio-template-wizard-extension.md) elementu.  
  
## <a name="remarks"></a>Poznámky  
 `FullClassName`je požadovaný podřízený element `WizardExtension`.  
  
## <a name="example"></a>Příklad  
 Následující příklad ilustruje metadata pro standardní projektu šablony pro [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] aplikací systému Windows.  
  
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
 [Postupy: použití průvodců se šablonami projektů](../extensibility/how-to-use-wizards-with-project-templates.md)