---
title: ProjectOutputFile – Element | Dokumentace Microsoftu
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- ProjectOutputFile element
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 2673b22bf502f019f0a10361c9d0cef9d5ac1b8c
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62816834"
---
# <a name="projectoutputfile-element"></a>ProjectOutputFile – element
  Představuje výstupní samostatný projekt obsahující položku projektu při nasazení do služby SharePoint.

## <a name="syntax"></a>Syntaxe

```xml
<ProjectOutputFile ProjectId = "GUID of the project"
    ProjectPath = "Relative path of the project"
    Target = "Deployment path of the project output"
    Type = "Type of deployment for the project output" />
```

## <a name="type"></a>Type
 **ProjectOutputFileType**

## <a name="attributes-and-elements"></a>Atributy a elementy
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.

### <a name="attributes"></a>Atributy

|Atribut|Popis|
|---------------|-----------------|
|**ProjectId**|Vyžaduje **xs:string** atribut.<br /><br /> Identifikátor GUID závislého projektu, který má výstup, který chcete zahrnout. To odpovídá **ProjectGuid** element v souboru závislý projekt.|
|**ProjectPath**|Vyžaduje **xs:string** atribut.<br /><br /> Relativní cesta, včetně názvu souboru projektu, závislého projektu, který má výstup, který chcete zahrnout. Tato cesta je relativní vzhledem ke kořenové složce Sharepointového projektu, který obsahuje položku Sharepointového projektu.|
|**Cíl**|Volitelné **xs:string** atribut.<br /><br /> Cesta, kam se výstup závislého projektu k nasazení na serveru SharePoint server vzhledem ke kořenové složky nasazení. Kořenové složky nasazení se určuje podle typ nasazení určený **typ** atribut.<br /><br /> Další informace najdete v popisech pro **cesty nasazení** a **kořen nasazení** položky v projektu služby SharePoint [řešení pro vývoj SharePoint](../sharepoint/developing-sharepoint-solutions.md).|
|**Typ**|Vyžaduje **xs:string** atribut.<br /><br /> Typ nasazení určený pro výstup závislého projektu. Další informace o možných hodnot, viz popis **typ nasazení** vlastnosti položky projektu služby SharePoint v [řešení vývoj služby SharePoint](../sharepoint/developing-sharepoint-solutions.md).|

### <a name="child-elements"></a>Podřízené prvky
 Žádné

### <a name="parent-elements"></a>Nadřazené prvky

|Prvek|Popis|
|-------------|-----------------|
|[Soubory](../sharepoint/files-element.md)|Určuje soubory, které chcete zahrnout do položky projektu služby SharePoint při nasazení do služby SharePoint.|

## <a name="remarks"></a>Poznámky
 Použití **ProjectOutputFile** – element pro zahrnutí výstupu projektu v nasazení položky projektu služby SharePoint. Můžete zadat jiný projekt, nebo stejný projekt, který obsahuje položky projektu. Další informace najdete v tématu [poskytují informace o balení a nasazení v položkách projektu](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md).

## <a name="element-information"></a>Informace o elementu

|||
|-|-|
|**Namespace**|http:\/\/schemas.microsoft.com/VisualStudio/<br>2010/SharePointTools/SharePointProjectItemModel|
|**Název schématu**|Schéma položky projektu služby SharePoint|
|**Soubor ověření**|ProjectItemModelSchema.xsd|
|**Může být prázdný**|Ne|

## <a name="see-also"></a>Viz také:
- [Referenční dokumentace schématu položek projektu služby SharePoint](../sharepoint/sharepoint-project-item-schema-reference.md)
- [Zadání informací o balení a nasazení v položkách projektu](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md)
- [Vývoj řešení služby SharePoint](../sharepoint/developing-sharepoint-solutions.md)
