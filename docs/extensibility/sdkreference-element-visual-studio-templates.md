---
title: SDKReference – – element (šablony sady Visual Studio) | Microsoft Docs
ms.date: 11/04/2016
ms.technology: vs-ide-general
ms.topic: reference
ms.assetid: 72c8b352-0b7a-42b3-ba5d-2a2d1e90c34b
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 2f43c813e688c1e175f1d36e6f06125f92404c48
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "80700166"
---
# <a name="sdkreference-element-visual-studio-templates"></a>SDKReference – element (šablony sady Visual Studio)
Určuje, že šablona položky používá odkaz na sadu SDK.

## <a name="syntax"></a>Syntax

```xml
<VSTemplate>
    <TemplateContent>
        <References>
            <Reference>
                <SDKReference>SDKname</SDKReference>
```

## <a name="attributes-and-elements"></a>Atributy a elementy
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.

### <a name="attributes"></a>Atributy
 Žádné

### <a name="child-elements"></a>Podřízené elementy
 Žádné

### <a name="parent-elements"></a>Nadřazené elementy

|Element|Popis|
|-------------|-----------------|
|[Odkaz](../extensibility/reference-element-visual-studio-templates.md)|Určuje odkaz na sestavení, který se má přidat při přidání položky do projektu.|

## <a name="text-value"></a>Textová hodnota
 Je vyžadována textová hodnota.

## <a name="remarks"></a>Poznámky
 Tento text určuje odkaz sady SDK, který se má přidat do projektu při vytvoření instance šablony položky.

```xml
<VSTemplate Version="3.0.0" xmlns="http://schemas.microsoft.com/developer/vstemplate/2005" Type="Item">
    <TemplateData> . . . </TemplateData>
    <TemplateContent>
        <References>
            <Reference>
                <SDKReference>Microsoft Visual C++ Runtime Package, Version=11.0.0.0</SDKReference>
...
```

## <a name="see-also"></a>Viz také
- [References – element (šablony sady Visual Studio)](../extensibility/references-element-visual-studio-templates.md)
- [Reference – element (šablony sady Visual Studio)](../extensibility/reference-element-visual-studio-templates.md)
- [Vytváření šablon projektů a položek](../ide/creating-project-and-item-templates.md)
- [Odkaz na schéma šablon sady Visual Studio](../extensibility/visual-studio-template-schema-reference.md)
