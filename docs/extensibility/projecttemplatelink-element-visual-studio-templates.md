---
title: ProjectTemplateLink – Element (šablony sady Visual Studio) | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#ProjectTemplateLink
helpviewer_keywords:
- <ProjectTemplateLink> element [Visual Studio Templates]
- ProjectTemplateLink element [Visual Studio Templates]
ms.assetid: b0449111-8b48-45a1-a031-ea24b765e969
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 3bc253967cf4f52d6e958b8b092f44f753bac2e9
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62805945"
---
# <a name="projecttemplatelink-element-visual-studio-templates"></a>ProjectTemplateLink – element (šablony sady Visual Studio)
Určuje cestu k *.vstemplate* souboru jednoho projektu ve víceprojektové šabloně.

 \<VSTemplate> \<TemplateContent> \<ProjectCollection> \<ProjectTemplateLink> -or- \<VSTemplate> \<TemplateContent> \<ProjectCollection> \<SolutionFolder> \<ProjectTemplateLink>

## <a name="syntax"></a>Syntaxe

```xml
<ProjectTemplateLink ProjectName="Name">
    PathToTemplateFile
</ProjectTemplateLink>
```

## <a name="attributes-and-elements"></a>Atributy a elementy
 Následující oddíly popisují atributy a podřízené a nadřazené elementy.

### <a name="attributes"></a>Atributy

|Atribut|Popis|
|---------------|-----------------|
|`ProjectName`|Nepovinný atribut.<br /><br /> Určuje název pro každý projekt ve víceprojektové šabloně. **Nový projekt** dialogové okno neumožňuje přiřadit názvy jednotlivých projektů.|
|`CopyParameters`|Umožňuje zkopírovat všechny proměnné z hlavní šablony skupiny do jednotlivých propojených šablon.<br /><br /> Parametry v propojených šablonách mají předponu `"$ext_*$"`. Například pokud v nadřazené šabloně skupiny parametr `$projectname$` má hodnotu **ExampleProject1**, když propojené šablony, získá má být spuštěna, parametr `$ext_projectname$`, což je kopie `$projectname$`parametr z nadřazené šabloně skupiny.<br /><br /> To umožňuje propojeným šablonám sdílet určité společné parametry, které stačí jednoduše vytvořit pouze v nadřazené šabloně skupiny.<br /><br /> Tento atribut je volitelný a bude automaticky výchozí `false` při případě začleněn není.<br /><br /> Zavedena v aplikaci Visual Studio 2013 Update 2. Tak, aby odkazovaly na správné verzi, najdete v článku [odkazovat na sestavení v aplikaci Visual Studio 2013 SDK Update 2](https://msdn.microsoft.com/library/42b65c3e-e42b-4c39-98c8-bea285f25ffb).|

### <a name="child-elements"></a>Podřízené prvky
 Žádné

### <a name="parent-elements"></a>Nadřazené prvky

|Prvek|Popis|
|-------------|-----------------|
|[ProjectCollection](../extensibility/projectcollection-element-visual-studio-templates.md)|Určuje uspořádání a obsah víceprojektových šablon.|
|[SolutionFolder](../extensibility/solutionfolder-element-visual-studio-templates.md)|Seskupuje projekty do víceprojektových šablon.|

## <a name="text-value"></a>Textová hodnota
 Je vyžadována textová hodnota.

 Tento text určuje cestu k *.vstemplate* souboru šablony.

## <a name="remarks"></a>Poznámky
 Šablony vícenásobných projektů slouží jako kontejnery pro dva nebo více projektů. `ProjectTemplateLink` Element slouží k určení umístění *.vstemplate* soubor pro některý z projektů v šabloně. *.Vstemplate* soubor víceprojektové šablony obsahuje jeden `ProjectTemplateLink` – element pro každý projekt v šabloně. Další informace o víceprojektových šablonách naleznete v tématu [jak: Vytváření šablon vícenásobného projektu](../ide/how-to-create-multi-project-templates.md).

## <a name="example"></a>Příklad
 Tento příklad ukazuje jednoduchý kořenový víceprojektové *.vstemplate* souboru. V tomto příkladu obsahuje šablona dva projekty `My Windows Application` a `My Class Library`. `ProjectName` Atribut na `ProjectTemplateLink` nastaví název elementu [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] tomuto projektu přiřadí. Pokud `ProjectName` atribut neexistuje, název *.vstemplate* soubor se používá jako název projektu.

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
            <ProjectTemplateLink ProjectName="My Class Library" CopyParameters="true">
                ClassLib\MyTemplate.vstemplate
            </ProjectTemplateLink>
        </ProjectCollection>
    </TemplateContent>
</VSTemplate>
```

## <a name="see-also"></a>Viz také:
- [Visual Studio odkaz na schéma šablon](../extensibility/visual-studio-template-schema-reference.md)
- [Vytváření šablon projektů a položek](../ide/creating-project-and-item-templates.md)
- [Postupy: Vytváření šablon vícenásobného projektu](../ide/how-to-create-multi-project-templates.md)