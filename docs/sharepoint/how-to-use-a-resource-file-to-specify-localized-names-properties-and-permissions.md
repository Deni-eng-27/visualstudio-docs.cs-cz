---
title: "Postupy: určení lokalizovaných názvů, vlastností a oprávnění pomocí zdrojového souboru | Microsoft Docs"
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
- VB
- CSharp
helpviewer_keywords:
- Business Data Connectivity service [SharePoint development in Visual Studio], localize strings
- BDC [SharePoint development in Visual Studio], localize strings
- BDC [SharePoint development in Visual Studio], resource file
- Business Data Connectivity service [SharePoint development in Visual Studio], resource strings
- BDC [SharePoint development in Visual Studio], properties
- Business Data Connectivity service [SharePoint development in Visual Studio], properties
- Business Data Connectivity service [SharePoint development in Visual Studio], resource file
- BDC [SharePoint development in Visual Studio], resource strings
ms.assetid: 72bb744d-818b-4e5a-9da2-295412025680
caps.latest.revision: "16"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 6a8b61477ae3b588b2aeadf1c9d99618151825f8
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-use-a-resource-file-to-specify-localized-names-properties-and-permissions"></a>Postupy: Určení lokalizovaných názvů, vlastností a oprávnění pomocí zdrojového souboru
  Pomocí souboru prostředků, můžete zadat lokalizované názvy, definovat vlastnosti a použít oprávnění tor objektů, které jsou definované v modelu služby Připojení obchodních dat (BDC). Zadejte tyto informace, můžete přidat **prostředků připojení obchodních dat** položku do projektu, který obsahuje **modelu připojení obchodních dat** položky. Potom zadejte názvy, vlastnosti a oprávnění tak, že upravíte soubor XML pro soubor prostředků.  
  
### <a name="to-add-a-bdc-resource-file-to-a-sharepoint-project"></a>Přidání souboru prostředků BDC do projektu služby SharePoint  
  
1.  V **Průzkumníku**, rozbalte složku projektu služby SharePoint a potom vyberte složku, která obsahuje modelu služby BDC.  
  
2.  Na řádku nabídek zvolte **projektu**, **přidat novou položku**.  
  
3.  Rozbalte **SharePoint** uzel a potom zvolte **2010** uzlu.  
  
4.  V **přidat novou položku** dialogovém okně vyberte **položka prostředků připojení obchodních dat**.  
  
5.  V **název** pole, zadejte název souboru prostředků a potom zvolte **přidat** tlačítko.  
  
     Soubor prostředků, který má příponu .bdcr je přidán do projektu a po otevření k úpravám.  
  
6.  Přidejte XML zadat lokalizovaných názvů, vlastností a oprávnění, která chcete použít modelu služby BDC.  
  
     Informace o tom, jak definovat tyto prvky najdete v tématu [modelu a soubory prostředků](http://go.microsoft.com/fwlink/?LinkID=169283).  
  
## <a name="see-also"></a>Viz také  
 [Postupy: Přidání stávajícího souboru modelu služby BDC do projektu služby SharePoint](../sharepoint/how-to-add-an-existing-bdc-model-file-to-a-sharepoint-project.md)   
 [Vytvoření modelu připojení obchodních dat](../sharepoint/creating-a-business-data-connectivity-model.md)   
 [Postupy: vytvoření modelu služby BDC](../sharepoint/how-to-create-a-bdc-model.md)   
 [Postupy: zahrnutí vlastního sestavení ve funkci BDC](../sharepoint/how-to-include-a-custom-assembly-in-a-bdc-feature.md)   
 [Integrace obchodních dat do služby SharePoint](../sharepoint/integrating-business-data-into-sharepoint.md)  
  
  