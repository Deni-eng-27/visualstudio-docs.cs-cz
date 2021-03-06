---
title: ProvideDefaultName – – element (šablony sady Visual Studio) | Microsoft Docs
ms.date: 11/04/2016
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#ProvideDefaultName
helpviewer_keywords:
- ProvideDefaultName element [Visual Studio project templates]
ms.assetid: 7b0e7b20-fd6b-42e2-81d0-e5100cea0528
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 192716198f605a5f6b4f62730e84dcf83b4229cc
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "80701721"
---
# <a name="providedefaultname-element-visual-studio-templates"></a>ProvideDefaultName – – element (šablony sady Visual Studio)
Určuje, zda [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] systém projektu bude generovat výchozí název šablony v dialogovém okně **Přidat novou položku** nebo **Nový projekt** .

 \<VSTemplate> \<TemplateData>
 \<ProvideDefaultName>

## <a name="syntax"></a>Syntax

```xml
<ProvideDefaultName> true/false </ProvideDefaultName>
```

## <a name="attributes-and-elements"></a>Atributy a elementy
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.

### <a name="attributes"></a>Atributy
 Žádné

### <a name="child-elements"></a>Podřízené elementy
 Žádné

### <a name="parent-elements"></a>Nadřazené prvky

|Element|Popis|
|-------------|-----------------|
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|Požadovaný element.<br /><br /> Zařadí šablonu do kategorie a definuje, jak se zobrazí v dialogovém okně **Nový projekt** nebo **Přidat novou položku** .|

## <a name="text-value"></a>Textová hodnota
 Je vyžadována textová hodnota.

 Text musí být buď `true` nebo `false` , který označuje, zda se má generovat výchozí název šablony v dialogovém okně **Přidat novou položku** nebo **Nový projekt** .

## <a name="remarks"></a>Poznámky
 `ProvideDefaultName` je volitelný prvek. Výchozí hodnota je `true`.

 Pokud `ProvideDefaultName` je element `false` , pole **název** v dialogových oknech **Přidat novou položku** a **Nový projekt** obsahují hodnotu `<Enter_name>` .

 Pomocí elementu [Default](../extensibility/defaultname-element-visual-studio-templates.md) zadejte výchozí název projektu nebo položky v dialogových oknech **Přidat novou položku** a **Nový projekt** . Pokud `ProvideDefaultName` je hodnota elementu `true` , vynechání `DefaultName` elementu pro projekty naplní dialogové okno názvem šablony, tedy hodnotou z elementu [Name](../extensibility/name-element-visual-studio-templates.md) .

## <a name="example"></a>Příklad
 Následující příklad kódu nastaví `ProvideDefaultName` element na `false` .

```
<VSTemplate Type="Item" Version="3.0.0"
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">
    <TemplateData>
        <Name>MyClass</Name>
        <Description>My custom C# class.</Description>
        <Icon>Icon.ico</Icon>
        <ProjectType>CSharp</ProjectType>
        <ProvideDefaultName>false</ProvideDefaultName>
    </TemplateData>
    <TemplateContent>
        <ProjectItem>MyClass.cs</ProjectItem>
    </TemplateContent>
</VSTemplate>
```

## <a name="see-also"></a>Viz také
- [Referenční dokumentace schématu šablon sady Visual Studio](../extensibility/visual-studio-template-schema-reference.md)
- [Vytváření šablon projektů a položek](../ide/creating-project-and-item-templates.md)
