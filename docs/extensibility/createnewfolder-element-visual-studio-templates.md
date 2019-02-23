---
title: Createnewfolder – Element (šablony sady Visual Studio) | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#CreateNewFolder
helpviewer_keywords:
- CreateNewFolder element [Visual Studio project templates]
ms.assetid: acef2016-4140-45d6-ace8-b8160eabd676
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 962a319477e63fdaa7b6f1982cd260ccb8d8bd7b
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56715105"
---
# <a name="createnewfolder-element-visual-studio-templates"></a>Createnewfolder – element (šablony sady Visual Studio)
Určuje, jestli se má zkontrolovat, že cílový adresář, ve kterém se má vytvořit projekt neexistuje. Pokud adresář neexistuje, lze vytvořit nový adresář pro projekt. Toto nastavení je obvykle přepsat `NewProjectRequiresNewFolder(VsTemplate)` příznak registru (`HKEY_LOCAL_MACHINE/SOFTWARE(/Wow6432Node)/Microsoft/VisualStudio/<version number>/Projects/<project GUID>`), že všechny běžné typy projektů použít k určení, zda chcete vytvořit nový projekt v novém adresáři.

 \<VSTemplate> \<TemplateData> \<CreateNewFolder>

## <a name="syntax"></a>Syntaxe

```
<CreateNewFolder>
    true/false
</CreateNewFolder>
```

## <a name="type"></a>Typ
 `Boolean`

## <a name="attributes-and-elements"></a>Atributy a elementy
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.

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

 Text musí být buď `true` nebo `false`, která udává, zda je či není by měla být vytvořena nová složka kontejneru při vytvoření projektu ze šablony.

## <a name="remarks"></a>Poznámky
 `CreateNewFolder` je volitelný prvek. Výchozí hodnota je `true`.

 Hodnota zadaná v `CreateNewFolder` element pouze kompilátorem respektovány [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Pokud podkladový systém projektu podporuje.

## <a name="example"></a>Příklad
 Následující příklad kódu určuje nechcete vytvořit novou složku, pokud je projekt vytvořen z šablony.

```
<VSTemplate Type="Project" Version="3.0.0"
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">
    <TemplateData>
        <Name>My template</Name>
        <Description>A basic template</Description>
        <Icon>TemplateIcon.ico</Icon>
        <ProjectType>CSharp</ProjectType>
        <CreateNewFolder>false</CreateNewFolder>
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
- [Visual Studio odkaz na schéma šablon](../extensibility/visual-studio-template-schema-reference.md)
- [Vytváření šablon projektů a položek](../ide/creating-project-and-item-templates.md)