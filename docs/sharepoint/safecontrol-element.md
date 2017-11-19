---
title: "SafeControl – Element | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords: SafeControl element
ms.assetid: e7c61749-fc73-412c-be30-4af5ff2a9fd2
caps.latest.revision: "11"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 8d9651c320e574c8db9fcafcb6e98f13e45eac1d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="safecontrol-element"></a>SafeControl – element
  Představuje prvek ASPX nebo webovou část, která je označeny jako bezpečné pro všechny uživatele pro přístup na všechny stránky ASPX na webu služby SharePoint.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<SafeControl Assembly = "Name of assembly that contains the safe control"  
    IsSafe = "true/false"  
    IsSafeAgainstScript = "true/false"  
    Name = "Name of this safe control entry"  
    Namespace = "Namespace of the safe control"  
    TypeName = "Type of the safe control" />  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
  
|Atribut|Popis|  
|---------------|-----------------|  
|**Sestavení**|Volitelné **xs:string** atribut.<br /><br /> Název sestavení, ve kterém je definovaný prvek ASPX nebo webové části. Ve výchozím nastavení používá tento atribut **$SharePoint.Project.AssemblyFullName$** nahraditelný parametr pro název sestavení. Další informace najdete v tématu [nahraditelné parametry](../sharepoint/replaceable-parameters.md).|  
|**IsSafe**|Volitelné **xs:boolean** atribut.<br /><br /> Určuje, jestli je zabezpečený nedůvěryhodným uživatelům přístup k řízení ASPX nebo webové části.|  
|**IsSafeAgainstScript**|Volitelné **xs:boolean** atribut.<br /><br /> Určuje, zda nedůvěryhodným uživatelům můžete zobrazit nebo upravit vlastnosti ASPX řízení nebo webové části.|  
|**Jméno**|Volitelné **xs:string** atribut.<br /><br /> Název této položky bezpečné ovládací prvek v kolekci.|  
|**Namespace**|Volitelné **xs:string** atribut.<br /><br /> Obor názvů řízení ASPX nebo webové části.|  
|**TypeName**|Volitelné **xs:string** atribut.<br /><br /> Název typu ovládacího prvku ASPX nebo webové části.|  
  
### <a name="child-elements"></a>Podřízené elementy  
 Žádné  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[SafeControls –](../sharepoint/safecontrols-element.md)|Představuje kolekci ovládacích prvků ASPX a webových částí, které jsou označeny jako bezpečné pro všechny uživatele pro přístup na všechny stránky ASPX na webu služby SharePoint.|  
  
## <a name="remarks"></a>Poznámky  
 Další informace o bezpečné ovládací prvky najdete v tématu [poskytování balení a informace o nasazení v položkách projektu](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md).  
  
## <a name="element-information"></a>Informace o elementu  
  
|||  
|-|-|  
|**Namespace**|http://schemas.microsoft.com/VisualStudio/2010/SharePointTools/SharePointProjectItemModel|  
|**Název schématu**|Schéma položky projektu SharePoint|  
|**Ověření souboru**|ProjectItemModelSchema.xsd|  
|**Nesmí být prázdné**|Ne|  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace schématu položek projektu služby SharePoint](../sharepoint/sharepoint-project-item-schema-reference.md)   
 [Poskytnutí balení a informace o nasazení v položkách projektu](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md)  
  
  