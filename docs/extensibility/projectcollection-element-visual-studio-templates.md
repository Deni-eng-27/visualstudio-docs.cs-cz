---
title: ProjectCollection – element (šablony sady Visual Studio) | Microsoft Docs
ms.date: 11/04/2016
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#ProjectCollection
helpviewer_keywords:
- <ProjectCollection> element [Visual Studio Templates]
- ProjectCollection element [Visual Studio Templates]
ms.assetid: deb27180-2035-49ed-b835-c47bb3cd2f8f
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 12a22ca28c90ed1df69529ed3004b417b5e04276
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "80701979"
---
# <a name="projectcollection-element-visual-studio-templates"></a>ProjectCollection – element (šablony sady Visual Studio)
Určuje uspořádání a obsah víceprojektových šablon.

 \<VSTemplate> \<TemplateContent>
 \<ProjectCollection>

## <a name="syntax"></a>Syntax

```xml
<ProjectCollection>
    <ProjectTemplateLink> ... </ProjectTemplateLink>
    <SolutionFolder> ... </SolutionFolder>
</ProjectCollection>
```

## <a name="attributes-and-elements"></a>Atributy a elementy
 Následující oddíly popisují atributy a podřízené a nadřazené elementy.

### <a name="attributes"></a>Atributy
 Žádné

### <a name="child-elements"></a>Podřízené prvky

|Element|Popis|
|-------------|-----------------|
|[ProjectTemplateLink](../extensibility/projecttemplatelink-element-visual-studio-templates.md)|Volitelný element.<br /><br /> Určuje projekt v šabloně více projektů.|
|[SolutionFolder](../extensibility/solutionfolder-element-visual-studio-templates.md)|Volitelný element.<br /><br /> Seskupuje projekty do víceprojektových šablon.|

### <a name="parent-elements"></a>Nadřazené prvky

|Element|Popis|
|-------------|-----------------|
|[TemplateContent](../extensibility/templatecontent-element-visual-studio-templates.md)|Požadovaný element.<br /><br /> Určuje obsah šablony.|

## <a name="remarks"></a>Poznámky
 Šablony vícenásobných projektů slouží jako kontejnery pro dva nebo více projektů. `ProjectCollection`Element se používá k určení projektů, které mají být v šabloně obsaženy. Další informace o šablonách více projektů naleznete v tématu [How to: Create Multi-Project Templates](../ide/how-to-create-multi-project-templates.md).

## <a name="example"></a>Příklad
 Tento příklad ukazuje jednoduchý soubor root *. vstemplate* pro více projektů. V tomto příkladu šablona obsahuje dva projekty `My Windows Application` a `My Class Library` . `ProjectName`Atribut na `ProjectTemplateLink` elementu nastaví název pro [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] přiřazení tohoto projektu. Pokud `ProjectName` atribut neexistuje, použije se jako název projektu název souboru *. vstemplate* .

```
<VSTemplate Version="3.0.0" Type="ProjectGroup"
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">
    <TemplateData>
        <Name>Multi-Project Template Sample</Name>
        <Description>An example of a multi-project template</Description>
        <Icon>Icon.ico</Icon>
        <ProjectType>VisualBasic</ProjectType>
    </TemplateData>
    <TemplateContent>
        <ProjectCollection>
            <ProjectTemplateLink ProjectName="My Windows Application">
                WindowsApp\MyTemplate.vstemplate
            </ProjectTemplateLink>
            <ProjectTemplateLink ProjectName="My Class Library">
                ClassLib\MyTemplate.vstemplate
            </ProjectTemplateLink>
        </ProjectCollection>
    </TemplateContent>
</VSTemplate>
```

## <a name="see-also"></a>Viz také
- [Referenční dokumentace schématu šablon sady Visual Studio](../extensibility/visual-studio-template-schema-reference.md)
- [Vytváření šablon projektů a položek](../ide/creating-project-and-item-templates.md)
- [Postupy: vytváření šablon více projektů](../ide/how-to-create-multi-project-templates.md)
