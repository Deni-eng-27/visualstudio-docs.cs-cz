---
title: '&lt;customHostSpecified&gt; – element (vývoj pro Office v sadě Visual Studio)'
titleSuffix: ''
ms.custom: seodec18
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- application manifests [Office development in Visual Studio], <customHostSpecified> element
- <customHostSpecified> element
- customHostSpecified element
author: John-Hart
ms.author: johnhart
manager: douge
ms.workload:
- office
ms.openlocfilehash: f59433c2c7dfcdcea4ab6f5d7fd620542ea20dc1
ms.sourcegitcommit: a205ff1b389fba1803acd32c54df7feb0ef7a203
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/20/2018
ms.locfileid: "53648791"
---
# <a name="ltcustomhostspecifiedgt-element-office-development-in-visual-studio"></a>&lt;customHostSpecified&gt; – element (vývoj pro Office v sadě Visual Studio)
  `customHostSpecified` Element označuje, že toto řešení není samostatné aplikace. Řešení pro systém Office obsahují komponenty, které se hostují uvnitř aplikace Microsoft Office.  
  
## <a name="syntax"></a>Syntaxe  
  
```xml
<customHostSpecified />  
```  
  
## <a name="elements-and-attributes"></a>Elementy a atributy  
 `customHostSpecified` Element se vyžaduje pro řešení Office. Tento element má `co.v1` obor názvů a určuje, zda toto nasazení obsahuje komponenty, která se nasadí v rámci vlastního hostitele, a není samostatné aplikace.  
  
 Tento element je podřízeným prvkem první `<entrypoint>` elementu v manifestu aplikace. Může existovat žádné další podřízené prvky v dané `<entrypoint>` element nebo [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] vyvolá chybu ověření během instalace.  
  
 Tento element nemá žádné atributy a žádné podřízené prvky.  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu ukazuje, `customHostSpecified` elementu v manifestu aplikace pro řešení Office. Tento příklad kódu je součástí většího příkladu určeného v [manifesty aplikace pro řešení Office](../vsto/application-manifests-for-office-solutions.md).  
  
```xml
<entryPoint>  
    <co.v1:customHostSpecified />  
</entryPoint>  
```  
  
## <a name="see-also"></a>Viz také:  
 [Manifesty aplikace pro řešení pro systém Office](../vsto/application-manifests-for-office-solutions.md)   
 [Manifesty nasazení pro řešení pro systém Office](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce – manifest aplikace](/visualstudio/deployment/clickonce-application-manifest)  
  
  