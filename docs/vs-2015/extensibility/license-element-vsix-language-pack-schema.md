---
title: Element licence (schéma jazykové sady VSIX) | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
ms.assetid: 57dac3b7-0cdd-405c-9af5-30ed9ca45e53
caps.latest.revision: 9
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: f1299d97cbda78049732d3367a9231272397e2ec
ms.sourcegitcommit: 26178b116cbf7353fee6ca989b8d872114f7b405
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/01/2020
ms.locfileid: "89284379"
---
# <a name="license-element-vsix-language-pack-schema"></a>License – element (schéma jazykové sady VSIX)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nepovinný parametr. Cesta k lokalizované verzi souboru s licencí pro rozšíření.  
  
## <a name="syntax"></a>Syntax  
  
```  
<License>FilePath\license.txt</License>  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
  
|Atribut|Popis|  
|---------------|-----------------|  
|Žádné||  
  
### <a name="child-elements"></a>Podřízené elementy  
  
|Element|Popis|  
|-------------|-----------------|  
|Žádné||  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Element|Popis|  
|-------------|-----------------|  
|[LanguagePack – element VSIX](../extensibility/vsixlanguagepack-element-vsix-language-pack-schema.md)|Povinná hodnota. Poskytuje kořenový prvek pro jazykovou sadu VSIX.|  
  
## <a name="text-value"></a>Textová hodnota  
 Relativní cesta k lokalizovanému souboru s licencí, která se má zobrazit  
  
## <a name="remarks"></a>Poznámky  
 Pokud `License` je definován element, pak se text určeného licenčního souboru zobrazí během instalace a uživatel musí licenci přijmout, aby bylo možné pokračovat.  
  
## <a name="element-information"></a>Informace o elementu  
  
|                 |                                                           |
|-----------------|-----------------------------------------------------------|
|    Obor názvů    | `http://schemas.microsoft.com/developer/vsx-schema-lp/2010` |
|   Název schématu   |                 Schéma jazykové sady VSIX                 |
| Soubor ověření |                VSIXLanguagePackSchema. xsd                 |
|  Může být prázdné   |                      Není                       |
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace schématu VSX Language Pack](../extensibility/vsx-language-pack-schema-reference.md)   
 [Lokalizace balíčků VSIX](../extensibility/localizing-vsix-packages.md)   
 [Referenční dokumentace schématu rozšíření VSIX 1,0](/previous-versions/dd393700(v=vs.110))
