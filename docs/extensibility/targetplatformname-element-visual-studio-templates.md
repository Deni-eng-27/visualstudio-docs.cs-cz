---
title: "Targetplatformname – Element (šablony sady Visual Studio) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3a6b1f45-b5d6-418e-add1-87ee8f15033d
caps.latest.revision: "5"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 10aa5bca7a71294c7dbe297e9e4befb5da485bb7
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="targetplatformname-element-visual-studio-templates"></a>TargetPlatformName – element (šablony sady Visual Studio)
Určuje platformu, která šablona cíle projektu. Tento element se používá k určení, že šablona projektu se používá k vytvoření [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] aplikace.  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
<VSTemplate>  
    <TemplateData>   
        <TargetPlatformName> OperatingSystem</TargetPlatformName>  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
 Žádné  
  
### <a name="child-elements"></a>Podřízené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[Requiredplatformversion –](../extensibility/requiredplatformversion-element-visual-studio-templates.md)|Určuje verzi operační systém, šablony cíle projektu.|  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|Rozděluje šablonu a definuje, jak se zobrazuje v buď **nový projekt** nebo **přidat novou položku** dialogové okno.|  
  
## <a name="text-value"></a>Textová hodnota  
 Je vyžadována textová hodnota.  
  
## <a name="remarks"></a>Poznámky  
 Text musí být **Windows**.  
  
## <a name="example"></a>Příklad  
 Tento příklad určuje, že šablona cíle projektu [!INCLUDE[win8](../debugger/includes/win8_md.md)] nebo novější.  
  
```xml  
<VSTemplate Type="Project" Version="3.0.0" xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">   
    <TemplateData>   
        <TargetPlatformName>Windows</TargetPlatformName>   
        <RequiredPlatformVersion>8</RequiredPlatformVersion>   
    </TemplateData>   
    <TemplateContent> </TemplateContent>  
</VSTemplate>  
```  
  
## <a name="see-also"></a>Viz také  
 [Vytváření šablon projektů a položek](../ide/creating-project-and-item-templates.md)   
 [Odkaz na schéma šablon sady Visual Studio](../extensibility/visual-studio-template-schema-reference.md)