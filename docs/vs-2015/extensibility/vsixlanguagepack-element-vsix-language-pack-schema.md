---
title: Element VSIXLanguagePack (VSIX Language Pack Schema) | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 767f5c22-8b87-49ca-92aa-a7a3f026469f
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: cf8e55e38ecf16577482955c30ea95c5a5980087
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42668080"
---
# <a name="vsixlanguagepack-element-vsix-language-pack-schema"></a>Element VSIXLanguagePack (VSIX Language Pack Schema)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [VSIXLanguagePack Element (VSIX Language Pack Schema)](https://docs.microsoft.com/visualstudio/extensibility/vsixlanguagepack-element-vsix-language-pack-schema).  
  
Požadováno. Obsahuje kořenový prvek pro jazykové sady VSIX. Jazykové sady VSIX obsahuje informace lokalizovaného instalačního balíčku VSIX.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<VSIXLanguagePack>  
  <LocalizedName>...</LocalizedName>  
  <LocalizedDescription>...</LocalizedDescription>  
  <MoreInfoURL>...</MoreInfoURL>  
  <License>...</License>  
</VSIXLanguagePack>  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`xmlns`|XML obor názvů, ve kterém je definována schématu jazykové sady VSIX.|  
  
## <a name="xmlns-attribute"></a>Atribut xmlns.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`http://schemas.microsoft.com/developer/vsx-schema-lp/2010`|Požadováno. Umístění souboru, který definuje schéma pro jazykové sady.|  
  
### <a name="child-elements"></a>Podřízené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[LocalizedName – Element](../extensibility/localizedname-element-vsix-language-pack-schema.md)|Požadováno. Lokalizovaný název rozšíření k instalaci.|  
|[LocalizedDescription – Element](../extensibility/localizeddescription-element-vsix-language-pack-schema.md)|Požadováno. Lokalizovaný popis rozšíření k instalaci.|  
|[MoreInfoURL – Element](../extensibility/moreinfourl-element-vsix-language-pack-schema.md)|Volitelné. Odkaz na lokalizované informace o rozšíření.|  
|[Licence – Element](../extensibility/license-element-vsix-language-pack-schema.md)|Volitelné. Cesta lokalizovanou verzi souboru s licencí pro rozšíření.|  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|Žádné||  
  
## <a name="element-information"></a>Informace o elementu  
  
|||  
|-|-|  
|Obor názvů|http://schemas.microsoft.com/developer/vsx-schema-lp/2010|  
|Název schématu|VSIX Language Pack Schema|  
|Soubor ověření|VSIXLanguagePackSchema.xsd|  
|Může být prázdné.|Ne|  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace schématu VSX Language Pack](../extensibility/vsx-language-pack-schema-reference.md)   
 [Lokalizace balíčků VSIX](../extensibility/localizing-vsix-packages.md)   
 [Referenční dokumentace schématu 1.0 rozšíření VSIX](http://msdn.microsoft.com/en-us/76e410ec-b1fb-4652-ac98-4a4c52e09a2b)

