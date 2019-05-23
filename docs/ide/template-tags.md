---
title: Přidat nebo upravit značky v šablonách projektů
ms.date: 04/30/2019
author: minsa110
ms.author: somin
manager: jillfra
ms.topic: reference
helpviewer_keywords:
- item templates, updating
- Visual Studio templates, updating
- project templates, updating
- updating templates [Visual Studio]
- template tagging, updating
- template tags, updating
ms.openlocfilehash: 4a5113fa7f420d58892e2737ec9196422486490e
ms.sourcegitcommit: cd21b38eefdea2cdefb53e68e7a30b868e78dd6b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/22/2019
ms.locfileid: "66038662"
---
# <a name="add-tags-to-project-templates"></a>Přidání značek do šablony projektu

Počínaje [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/) verze 16.1 ve verzi Preview 2, můžete přidat jazyk, platformu a značky typu projektu do šablon projektu. Značky se používají na dvou místech v dialogovém okně Nový projekt:

- Značky se zobrazí v části Popis šablony

   ![Šablona projektu se značkami v dialogovém okně Nový projekt](media/npd-item-with-template-tags.png)

- Značky umožňují šablonu, kterou chcete vyhledávat a filtrovat

   ![Vyhledávání a filtrování v dialogovém okně Nový projekt](media/npd-search-and-filter.png)

Můžete přidat značky aktualizací *.vstemplate* souborů XML pomocí šablony značky integrované do sady Visual Studio, případně můžete vytvořit vlastní šablonu značky. Značky šablony objevit jenom v dialogové okno nového projektu aplikace Visual Studio 2019. Neovlivňují vykreslování šablony v předchozích verzích sady Visual Studio.

## <a name="add-or-edit-tags"></a>Přidat nebo upravit značky

Můžete chtít přidat nebo upravit značky v šabloně projektu *.vstemplate* XML při můžete:

* [Vytvořte novou šablonu projektu](/visualstudio/ide/how-to-create-project-templates) s použitím Průvodce exportem šablony

* [Aktualizovat stávající šablonu projektu](/visualstudio/ide/how-to-update-existing-templates)

* [Vytvoření nové šablony projektu VSIX](/visualstudio/extensibility/getting-started-with-the-vsix-project-template)

## <a name="syntax"></a>Syntaxe

```xml
<LanguageTag> Language Name </LanguageTag>
<PlatformTag> Platform Name </PlatformTag>
<ProjectTypeTag> Project Type </ProjectTypeTag>
```

## <a name="attributes"></a>Atributy

Následující atributy jsou volitelné a pro scénáře pro pokročilé uživatele.

|Atribut|Popis|
|---------------|-----------------|
|`Package`|Identifikátor GUID, který určuje balíček sady Visual Studio.|
|`ID`|Určuje ID prostředku. Visual Studio|

Syntaxe:

```xml
<LanguageTag Package="{PackageID}" ID="ResourceID" />
<PlatformTag Package="{PackageID}" ID="ResourceID" />
<ProjectTypeTag Package="{PackageID}" ID="ResourceID" />
```

## <a name="elements"></a>Elementy

### <a name="child-elements"></a>Podřízené prvky

Žádné

### <a name="parent-elements"></a>Nadřazené prvky

|Prvek|Popis|
|-------------|-----------------|
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|(Povinné) Rozděluje šablonu a definuje, jak se zobrazuje **nový projekt** nebo **přidat novou položku** dialogové okno.|

## <a name="text-value"></a>Textová hodnota

Pokud je vyžadována textová hodnota `Package` a `ID` atributy se používají.

Text obsahuje název šablony.

## <a name="built-in-tags"></a>Integrované značky

Visual Studio nabízí že seznam integrovaných značek, který při přidání, vykreslení lokalizovaný prostředek. Následuje seznam integrovaných značek a jejich odpovídající hodnoty v závorkách.

| Jazyk | Platforma | Typ projektu |
| -- | -- | -- |
| C++ (`cpp`) | Android (`android`) | Cloud (`cloud`) |
| C#(`csharp`) | Azure (`azure`) | Konzoly (`console`) |
| F#(`fsharp`) | iOS (`ios`) | Desktop (`desktop`) |
| Java (`java`) | Linux (`linux`) | Rozšíření (`extension`) |
| JavaScript (`javascript`) | macOS (`macos`) | Hry (`games`) |
| Python (`python`) | tvOS (`tvos`) | IoT (`iot`) |
| Dotaz Languate (`querylanguage`) | Windows (`windows`) | Knihovna (`library`) |
| TypeScript (`typescript`) | Xbox (`xbox`) | Machine Learning (`machinelearning`) |
| Visual Basic (`visualbasic`) | | Mobilní zařízení (`mobile`) |
| | | Office (`office`) |
| | | Ostatní (`other`) |
| | | Služby (`service`) |
| | | Test (`test`) |
| | | UWP (`uwp`) |
| | | Web (`web`) |

## <a name="example"></a>Příklad

Následující příklad ukazuje metadata pro šablony projektu pro vizuál C# aplikace.

```xml
<VSTemplate Type="Project" Version="3.0.0"
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">
    <TemplateData>
        <Name>My template</Name>
        <Description>A basic template</Description>
        <Icon>TemplateIcon.ico</Icon>
        <ProjectType>CSharp</ProjectType>
        <LanguageTag>C#</LanguageTag>
        <PlatformTag>windows</PlatformTag>
        <PlatformTag>linux</PlatformTag>
        <PlatformTag>My Platform</PlatformTag>
        <ProjectTypeTag>console</ProjectTypeTag>
        <ProjectTypeTag>desktop</ProjectTypeTag>
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

- [Visual Studio odkaz na schéma šablon](/visualstudio/extensibility/visual-studio-template-schema-reference)
- [Vytváření šablon projektů a položek](/visualstudio/ide/creating-project-and-item-templates)
- [Přizpůsobení šablon projektů a položek](/visualstudio/ide/customizing-project-and-item-templates)
- [Začínáme se šablonou projektu VSIX](/visualstudio/extensibility/getting-started-with-the-vsix-project-template)