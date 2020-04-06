---
title: Element WizardExtension (šablony sady Visual Studio) | Dokumenty společnosti Microsoft
ms.date: 11/04/2016
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#WizardExtension
helpviewer_keywords:
- WizardExtension element [Visual Studio Templates]
- <WizardExtension> element [Visual Studio Templates]
ms.assetid: d54b01c1-50f5-4b65-828c-686e2321cc8c
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: fd81b32861114d654aa794b992826589406b1df9
ms.sourcegitcommit: 16a4a5da4a4fd795b46a0869ca2152f2d36e6db2
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/06/2020
ms.locfileid: "80740370"
---
# <a name="wizardextension-element-visual-studio-templates"></a>WizardExtension – element (šablony sady Visual Studio)
Obsahuje registrační prvky pro přizpůsobení průvodce šablonou.

 \<VSTemplate> ... \<> rozšíření průvodce

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
 Žádné.

### <a name="child-elements"></a>Podřízené elementy

|Element|Popis|
|-------------|-----------------|
|[Sestavení](../extensibility/assembly-element-visual-studio-template-wizard-extension.md)|Požadovaný element.<br /><br /> Určuje název nebo silný název sestavení, které se zobrazí v globální mezipaměti sestavení. Musí být alespoň `Assembly` jeden prvek `WizardExtension` v prvku.|
|[FullClassName](../extensibility/fullclassname-element-visual-studio-template-wizard-extension.md)|Požadovaný element.<br /><br /> Plně kvalifikovaný název třídy, která `IWizard` implementuje rozhraní. Musí být alespoň `FullClassName` jeden prvek `WizardExtension` v prvku.|

### <a name="parent-elements"></a>Nadřazené elementy

|Element|Popis|
|-------------|-----------------|
|[VSTemplate](../extensibility/vstemplate-element-visual-studio-templates.md)|Obsahuje všechna metadata pro šablonu projektu, šablonu položky nebo startovní soupravu.|

## <a name="remarks"></a>Poznámky
 `WizardExtension`je volitelný podřízený `VSTemplate`prvek .

## <a name="example"></a>Příklad
 Následující příklad ilustruje metadata pro standardní šablonu [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] projektu pro aplikaci systému Windows.

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
- [Odkaz na schéma šablon sady Visual Studio](../extensibility/visual-studio-template-schema-reference.md)
- [Vytváření šablon projektů a položek](../ide/creating-project-and-item-templates.md)
- [Postupy: Použití průvodců se šablonami projektů](../extensibility/how-to-use-wizards-with-project-templates.md)
