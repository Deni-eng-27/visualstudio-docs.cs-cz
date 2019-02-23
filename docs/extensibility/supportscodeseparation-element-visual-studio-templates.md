---
title: Supportscodeseparation – Element (šablony sady Visual Studio) | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#SupportsCodeSeparation
helpviewer_keywords:
- SupportsCodeSeparation element [Visual Studio Templates]
- <SupportsCodeSeparation> element [Visual Studio Templates]
ms.assetid: 8112aac8-a269-40e5-b92b-9b9a6ff5a542
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 504e176973cd9bb6f0041254e0de19d675be05df
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56716464"
---
# <a name="supportscodeseparation-element-visual-studio-templates"></a>SupportsCodeSeparation – element (šablony sady Visual Studio)
Určuje, zda **umístěte kód v samostatném souboru** zaškrtávací políčko je dostupné v **přidat novou položku** dialogové okno.

 \<Vstemplate – > \<TemplateData > \<supportscodeseparation – >

## <a name="syntax"></a>Syntaxe

```
<SupportsCodeSeparation> true/false </SupportsCodeSeparation>
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
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|Požadovaný element.<br /><br /> Rozděluje šablonu a definuje, jak se zobrazuje **nový projekt** nebo **nová položka** dialogové okno.|

## <a name="text-value"></a>Textová hodnota
 Je vyžadována textová hodnota.

 Text musí být buď `true` nebo `false`, která udává, zda je či není **umístěte kód v samostatném souboru** zaškrtávací políčko je dostupné v **přidat novou položku** dialogové okno.

## <a name="remarks"></a>Poznámky
 `SupportsCodeSeparation` je volitelný prvek. Výchozí hodnota je `false`.

 `SupportsCodeSeparation` Element je dostupná jenom pro webové šablony položek.

 Oddělení kódu nebo použití modelu code-behind model stránky, umožňuje uchovávat značky v jednom souboru a programový kód do jiného souboru. [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] a jinými jazyky rozhraní .NET použijte tento model.

## <a name="example"></a>Příklad
 Následující příklad určuje zobrazíte **umístěte kód v samostatném souboru** možnost.

```
<VSTemplate Version="3.0.0" Type="Project"
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">>
    <TemplateData>
        <Name>MyWebProjecStarterKit</Name>
        <Description>A simple Web template</Description>
        <Icon>icon.ico</Icon>
        <ProjectType>Web</ProjectType>
        <ProjectSubType>CSharp</ProjectSubType>
        <DefaultName>WebSite</DefaultName>
        <SupportsCodeSeparation>true</SupportsCodeSeparation>
    </TemplateData>
    <TemplateContent>
        <Project File="WebApplication.webproj">
            <ProjectItem>icon.ico</ProjectItem>
            <ProjectItem OpenInEditor="true">Default.aspx</ProjectItem>
            <ProjectItem>Default.aspx.cs</ProjectItem>
        </Project>
    </TemplateContent>
</VSTemplate>
```

## <a name="see-also"></a>Viz také
- [Odkaz na schéma šablon sady Visual Studio](../extensibility/visual-studio-template-schema-reference.md)
- [Vytváření šablon projektů a položek](../ide/creating-project-and-item-templates.md)