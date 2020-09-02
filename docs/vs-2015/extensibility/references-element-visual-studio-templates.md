---
title: References – element (šablony sady Visual Studio) | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#References
helpviewer_keywords:
- <References> element [Visual Studio Templates]
- References element [Visual Studio Templates]
ms.assetid: 1969146d-46bf-422d-8d46-0e9493925003
caps.latest.revision: 9
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 19fd3e260e6c7079ccfb98f520858a31191cc112
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "62538210"
---
# <a name="references-element-visual-studio-templates"></a>Element odkazů (šablony sady Visual Studio)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Seskupí sestavení odkazuje na to, že šablona přičítá k projektům.  
  
 \<VSTemplate>  
 \<TemplateContent>  
 \<References>  
  
## <a name="syntax"></a>Syntax  
  
```  
<References>  
    <Reference>... </Reference>  
    <Reference>... </Reference>  
    ...  
</References>  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující oddíly popisují atributy a podřízené a nadřazené elementy.  
  
### <a name="attributes"></a>Atributy  
 Žádné  
  
### <a name="child-elements"></a>Podřízené elementy  
  
|Element|Popis|  
|-------------|-----------------|  
|[Odkaz](../extensibility/reference-element-visual-studio-templates.md)|Požadovaný element.<br /><br /> Určuje odkaz na sestavení, který se má přidat při přidání položky do projektu. V elementu musí být jeden nebo více `Reference` elementů `References` .|  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Element|Popis|  
|-------------|-----------------|  
|[TemplateContent](../extensibility/templatecontent-element-visual-studio-templates.md)|Určuje obsah šablony.|  
  
## <a name="remarks"></a>Poznámky  
 `References` je volitelný podřízený prvek elementu `TemplateContent` .  
  
 `Reference`Elementy a `References` lze použít pouze v souborech. vstemplate, které mají `Type` hodnotu atributu `Item` .  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje `TemplateContent` prvek šablony položky. Tento kód XML přidá odkazy na System.dll a System.Data.dll sestavení.  
  
```  
<TemplateContent>  
    <References>  
        <Reference>  
            <Assembly>  
                System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089  
            </Assembly>  
        </Reference>  
        <Reference>  
            <Assembly>  
                System.Data, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089  
            </Assembly>  
        </Reference>  
    </References>  
    ...  
</TemplateContent>  
```  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace schématu šablon sady Visual Studio](../extensibility/visual-studio-template-schema-reference.md)   
 [Vytváření šablon projektů a položek](../ide/creating-project-and-item-templates.md)
