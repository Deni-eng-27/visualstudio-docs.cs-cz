---
title: "&lt;Popis&gt; – Element (vývoj pro Office v sadě Visual Studio) | Microsoft Docs"
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
helpviewer_keywords:
- description element
- <description> element
- application manifests [Office development in Visual Studio], <description> element
ms.assetid: 27c90f8c-393d-4557-9371-2e4e3c4a2d95
caps.latest.revision: "21"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: a4978233c9172dd07cc034cba7f0d0f76374f231
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="ltdescriptiongt-element-office-development-in-visual-studio"></a>&lt;Popis&gt; – Element (vývoj pro Office v sadě Visual Studio)
  `description` Element `vstov4` obor názvů ukládá popis řešení Office, který se zobrazí v dialogovém okně Doplňky COM z aplikace Microsoft Office.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<description>  
</description>  
```  
  
## <a name="elements-and-attributes"></a>Elementy a atributy  
 Volitelné. `description` Elementu je `vstov4` oboru názvů. Obsahuje popis doplněk, který se zobrazí v dialogovém okně Doplňky COM z aplikace Microsoft Office.  
  
 `description` Element nemá žádné atributy nebo elementy.  
  
## <a name="vsto-add-in-example"></a>Příklad doplňku VSTO  
  
### <a name="description"></a>Popis  
 Následující příklad kódu ukazuje `description` element pro řešení s úrovni aplikace nasazené pomocí [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]. Tento příklad kódu je součástí většího příkladu vztahujícího se v [manifesty aplikací pro řešení Office](../vsto/application-manifests-for-office-solutions.md).  
  
### <a name="code"></a>Kód  
  
```  
<vstov4:description>  
  ContosoOutlookAddIn - Outlook add-in   
  created with Visual Studio Tools for Office  
</vstov4:description>  
```  
  
## <a name="see-also"></a>Viz také  
 [Manifesty aplikace pro řešení pro systém Office](../vsto/application-manifests-for-office-solutions.md)   
 [Manifesty nasazení pro řešení Office](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce – Manifest aplikace](/visualstudio/deployment/clickonce-application-manifest)  
  
  