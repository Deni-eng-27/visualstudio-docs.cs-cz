---
title: 'Postupy: Generování šablon ze šablon pomocí řídicích sekvencí | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
helpviewer_keywords:
- text templates, generating templates from templates
ms.assetid: 4126156a-7cea-48b8-925e-7790806cfe6c
caps.latest.revision: 37
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 4a3ddd7896732c5b87c5b6bd2032c27fffd96a41
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62546619"
---
# <a name="how-to-generate-templates-from-templates-by-using-escape-sequences"></a>Postupy: Generování šablon ze šablon pomocí řídicích sekvencí
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Můžete vytvořit textové šablony, která vytvoří jiné textové šablony jako jeho vygenerovaný textový výstup. Chcete-li to provést, musíte použít řídicí sekvence od sebe odděluje textové šablony značky. Pokud nepoužijete řídicí sekvence, generované textové šablony se mají předem definované význam. Další informace o použití řídicích sekvencí v textových šablonách naleznete v tématu [pomocí řídicích sekvencí v textových šablonách](../modeling/using-escape-sequences-in-text-templates.md).  
  
### <a name="to-generate-a-text-template-from-within-a-text-template"></a>Ke generování textové šablony z v rámci textové šablony  
  
- Použít zpětné lomítko (\\) jako řídicí znak vytvářel potřebné značky v rámci textové šablony pro direktivy, příkazy, výrazy a funkce v samostatném textovém souboru šablony třídy.  
  
    ```  
    \<#@ directive \#>  
    \<# statement \#>  
    \<#= expression \#>  
    \<#+ classfeature \#>  
    ```  
  
## <a name="example"></a>Příklad  
 Následující příklad používá řídicí znaky pro vytvoření textové šablony z textové šablony. `output` – Direktiva nastaví cílový typ souboru pro typ souboru textové šablony (.tt).  
  
```csharp  
\<#@ output extension=".tt" \#>  
\<#@ assembly name="System.Xml.dll" \#>  
\<#@ import namespace="System.Xml" \#>  
\<#  
XmlDocument xDoc = new XmlDocument();  
//System.Diagnostics.Debugger.Break();  
    xDoc.Load(@"E:\CSharp\Overview.xml");  
    XmlAttributeCollection attributes = xDoc.Attributes;  
    if (attributes != null)  
    {  
       foreach (XmlAttribute attr in attributes)  
       {\#>  
           \<#= attr.Name \#>  
       \<#}  
     }  
\#>  
```  
  
 Vygenerovaný textový výstup je textové šablony.  
  
```  
<#@ output extension=".tt" #>  
<#@ assembly name="System.Xml.dll" #>  
<#@ import namespace="System.Xml" #>  
<#  
XmlDocument xDoc = new XmlDocument();  
//System.Diagnostics.Debugger.Break();  
    xDoc.Load(@"E:\CSharp\Overview.xml");  
    XmlAttributeCollection attributes = xDoc.Attributes;  
    if (attributes != null)  
    {  
       foreach (XmlAttribute attr in attributes)  
       {#>  
           <#= attr.Name #>  
       <#}  
     }  
#>  
```
