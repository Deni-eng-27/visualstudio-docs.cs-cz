---
title: '&lt;formRegion&gt; – Element (vývoj pro Office v sadě Visual Studio) | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- application manifests [Office development in Visual Studio], <formRegion> element
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: af7dd4f3472692def9f05a937297d54d13c6f0d6
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="ltformregiongt-element-office-development-in-visual-studio"></a>&lt;formRegion&gt; – Element (vývoj pro Office v sadě Visual Studio)
  `formRegion` Element `vstov4` obor názvů identifikuje oblasti formuláře aplikace Microsoft Office Outlook, která souvisí s doplňku VSTO.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<formRegion  
  name>  
  <messageClass  
    name/>  
</formRegion>  
```  
  
## <a name="elements-and-attributes"></a>Elementy a atributy  
 `formRegion` Element `vstov4` obor názvů identifikuje oblasti formuláře, který je přidružen doplňku VSTO v Outlooku. Je vyžadována pouze pro aplikaci Outlook doplňků VSTO obsahující oblasti formulářů.  
  
 Může být více `formRegion` elementy definované uvnitř `formRegions` element pro jeden Add-in VSTO.  
  
 `formRegion` Element má následující atribut.  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`name`|Požadováno. Určuje název oblasti formuláře.|  
  
 `formRegion` Element má následující podřízené prvky.  
  
### <a name="messageclass"></a>Třída messageClass  
 `messageClass` Element identifikuje formuláře aplikace Outlook, který je přidružen oblasti formuláře.  
  
 `messageClass` Element má následující atribut.  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`name`|Požadováno. Identifikuje formulář, který je přidružen oblasti formuláře.|  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu ukazuje `formRegion` element v manifestu aplikace pro Outlook VSTO doplňku nasadit pomocí [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]. Existují tři zpráva třídy přidružené k této oblasti jednoho formuláře. Tento příklad kódu je součástí většího příkladu vztahujícího se v [manifesty aplikací pro řešení Office](../vsto/application-manifests-for-office-solutions.md).  
  
```  
<vstov4:formRegion  
    name="OutlookAddIn1.FormRegion1">  
  <vstov4:messageClass name="IPM.Note" />  
  <vstov4:messageClass name="IPM.Contact" />  
  <vstov4:messageClass name="IPM.Appointment" />  
</vstov4:formRegion>  
```  
  
## <a name="see-also"></a>Viz také  
 [Vytváření oblastí formulářů aplikace Outlook](../vsto/creating-outlook-form-regions.md)   
 [Manifesty aplikace pro řešení pro systém Office](../vsto/application-manifests-for-office-solutions.md)   
 [Manifesty nasazení pro řešení Office](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce – manifest aplikace ](/visualstudio/deployment/clickonce-application-manifest)  
  
  