---
title: '&lt;přizpůsobení&gt; – element (vývoj pro Office v sadě Visual Studio)'
titleSuffix: ''
ms.custom: seodec18
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- application manifests [Office development in Visual Studio], <customization> element
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 798cb2e7a8526e97a3d97240e181ef2e35ed21b1
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62956057"
---
# <a name="ltcustomizationgt-element-office-development-in-visual-studio"></a>&lt;přizpůsobení&gt; – element (vývoj pro Office v sadě Visual Studio)
  `customization` Elementu `vstov4` obor názvů popisuje konkrétní řešení Office. Podřízené prvky se liší pro přizpůsobení na úrovni dokumentu a doplňky VSTO.

## <a name="syntax-for-document-level-customizations"></a>Syntaxe pro přizpůsobení na úrovni dokumentu

```xml
<customization
  id
  <document
    solutionId
  />
</customization>
```

## <a name="syntax-for-vsto-add-ins"></a>Syntaxe pro doplňky VSTO

```xml
<customization
  id
  <appAddin
    application
    loadBehavior
    keyName>
  <friendlyName></friendlyName>
  <description></description>
  <formRegions></formRegions>
</customization>
```

## <a name="elements-and-attributes"></a>Elementy a atributy
 `customization` Prvek obsahuje informace specifické pro přizpůsobení. Tento element musí být v následujícím oboru názvů: `vstov4=urn:schemas-microsoft-com:vsto.v4`. Existuje jedna `customization` – element pro každé řešení Office. Například pokud nasadíte tři řešení pro systém Office v nasazení více projekty, existují tři `customization` prvky v manifestu aplikace.

 Podřízené prvky prvku sestavení musí být také v tomto oboru názvů.

 `customization` Element má tento atribut.

|Atribut|Popis|
|---------------|-----------------|
|`id`|Vyžaduje se pro nasazení více projekty. `id` Element jednoznačně identifikuje řešení pro Office.|

### <a name="document-level-customizations"></a>Přizpůsobení na úrovni dokumentu
 `customization` Element má následující podřízený prvek.

#### <a name="document"></a>dokument
 `document` Prvek `vstov4` obor názvů je definovaný v [ &#60;dokumentu&#62; element &#40;vývoj pro Office v sadě Visual Studio&#41;](../vsto/document-element-office-development-in-visual-studio.md).

### <a name="vsto-add-ins"></a>Doplňky VSTO
 `customization` Element má následující podřízený prvek.

#### <a name="appaddin"></a>appAddin
 `appAddin` Prvek `vstov4` obor názvů je definovaný v [ &#60;appAddin&#62; element &#40;vývoj pro Office v sadě Visual Studio&#41;](../vsto/appaddin-element-office-development-in-visual-studio.md).

## <a name="example-of-a-document-level-customization"></a>Příklad přizpůsobení na úrovni dokumentu

### <a name="description"></a>Popis
 Následující příklad kódu ukazuje, `customization` – element pro přizpůsobení na úrovni dokumentu. Tento příklad kódu je součástí většího příkladu určeného v [manifesty aplikace pro řešení Office](../vsto/application-manifests-for-office-solutions.md).

### <a name="code"></a>Kód

```xml
<vstov4:customization>
  <vstov4:document
    solutionId="73e" />
</vstov4:customization>
```

## <a name="example-of-a-vsto-add-in"></a>Příklad doplňku VSTO

### <a name="description"></a>Popis
 Následující příklad kódu ukazuje, `customization` – element pro doplňku VSTO. Toto je VSTO pro Outlook doplněk, který zahrnuje oblasti formuláře. Tento příklad kódu je součástí většího příkladu určeného v [manifesty aplikace pro řešení Office](../vsto/application-manifests-for-office-solutions.md).

### <a name="code"></a>Kód

```xml
<vstov4:customization>
  <vstov4:appAddIn
    application="Outlook"
    loadBehavior="3"
    keyName="ContosoOutlookAddIn">
    <vstov4:friendlyName>
      ContosoOutlookAddIn
    </vstov4:friendlyName>
    <vstov4:description>
      ContosoOutlookAddIn - Outlook VSTO Add-in
      created with Visual Studio Tools for Office
    </vstov4:description>
    <vstov4:formRegions>
      <vstov4:formRegion
          name="OutlookAddIn1.FormRegion1">
        <vstov4:messageClass name="IPM.Note" />
        <vstov4:messageClass name="IPM.Contact" />
        <vstov4:messageClass name="IPM.Appointment" />
      </vstov4:formRegion>
    </vstov4:formRegions>
  </vstov4:appAddIn>
</vstov4:customization>
```

## <a name="see-also"></a>Viz také:

- [Manifesty aplikace pro řešení pro systém Office](../vsto/application-manifests-for-office-solutions.md)
- [Manifesty nasazení pro řešení pro systém Office](../vsto/deployment-manifests-for-office-solutions.md)
- [ClickOnce – manifest aplikace](../deployment/clickonce-application-manifest.md)