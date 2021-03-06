---
title: Vygenerování textové šablony z textové šablony
description: Poskytuje informace o tom, jak vygenerovat textovou šablonu z jiné textové šablony pomocí řídicích sekvencí.
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- text templates, generating templates from templates
author: JoshuaPartlow
ms.author: joshuapa
manager: jillfra
ms.custom: SEO-VS-2020
ms.workload:
- multiple
ms.openlocfilehash: d7ef983525842023247433e7a3c2b51e206a1cee
ms.sourcegitcommit: a18c7e9b367c2f92f6e54c3eaef442775d457667
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/15/2020
ms.locfileid: "90100758"
---
# <a name="how-to-generate-templates-from-templates-by-using-escape-sequences"></a>Postupy: Generování šablon ze šablon pomocí řídicích sekvencí
Můžete vytvořit textovou šablonu, která vytvoří další textovou šablonu jako vygenerovaný textový výstup. K tomu je nutné použít řídící sekvence k vymezení tagů textových šablon. Pokud nepoužíváte řídicí sekvence, vaše vytvořená šablona textu bude mít předem definovaný význam. Další informace o použití řídicích sekvencí v textových šablonách naleznete v tématu [Použití řídicích sekvencí v textových šablonách](../modeling/using-escape-sequences-in-text-templates.md).

### <a name="to-generate-a-text-template-from-within-a-text-template"></a>Vygenerování textové šablony v rámci textové šablony

- Pomocí zpětného lomítka ( \\ ) jako řídicího znaku vytvořte potřebné značky značek v rámci textové šablony pro direktivy, příkazy, výrazy a funkce třídy v samostatném souboru textové šablony.

    ```
    \<#@ directive \#>
    \<# statement \#>
    \<#= expression \#>
    \<#+ classfeature \#>
    ```

## <a name="example"></a>Příklad
 Následující příklad používá řídicí znaky k vytvoření textové šablony z textové šablony. `output`Direktiva nastaví typ cílového souboru na typ souboru textové šablony (. TT).

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

 Generovaný textový výstup je textová šablona.

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
