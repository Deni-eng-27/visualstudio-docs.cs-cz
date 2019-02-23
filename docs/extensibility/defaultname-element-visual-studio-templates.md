---
title: Defaultname – Element (šablony sady Visual Studio) | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#DefaultName
helpviewer_keywords:
- DefaultName element [Visual Studio project templates]
ms.assetid: 0ff056c8-b9d2-4747-9308-92adf1811491
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: bc859155afcde0b72b8898b2ea37c098f7458e53
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56717452"
---
# <a name="defaultname-element-visual-studio-templates"></a>Defaultname – element (šablony sady Visual Studio)
Určuje název, který vygeneruje systém projektu sady Visual Studio pro projekt nebo položku při jeho vytvoření.

 \<Vstemplate – > \<TemplateData > \<defaultname – >

## <a name="syntax"></a>Syntaxe

```
<DefaultName>
    Default Project Name
</DefaultName>
```

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

 Tento text určuje výchozí název projektu nebo položky.

## <a name="remarks"></a>Poznámky
 `DefaultName` je volitelný prvek.

 Pro projekty tento prvek určuje název adresáře, který ukládá projektu na disku. Pro položky Určuje název souboru zdrojového souboru.

 Při vytváření projektu nebo položky, můžete upravit pomocí výchozí název **název** možnost, která je k dispozici buď z **nový projekt** dialogové okno nebo **přidat novou položku** Dialogové okno.

 Pokud nechcete, aby systém projektu k vygenerování výchozího názvu pro projekt nebo položku, nastavte [providedefaultname –](../extensibility/providedefaultname-element-visual-studio-templates.md) elementu `False`.

## <a name="example"></a>Příklad
 Následující příklad ukazuje metadata pro šablony pro standardní položky [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] třídy.

```
<VSTemplate Type="Item" Version="3.0.0"
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">
    <TemplateData>
        <Name>MyClass</Name>
        <Description>My custom C# class.</Description>
        <Icon>Icon.ico</Icon>
        <ProjectType>CSharp</ProjectType>
        <DefaultName>MyClass.cs</DefaultName>
    </TemplateData>
    <TemplateContent>
        <ProjectItem ReplaceParameters="true">MyClass.cs</ProjectItem>
    </TemplateContent>
</VSTemplate>
```

## <a name="see-also"></a>Viz také:
- [Visual Studio odkaz na schéma šablon](../extensibility/visual-studio-template-schema-reference.md)
- [Vytváření šablon projektů a položek](../ide/creating-project-and-item-templates.md)