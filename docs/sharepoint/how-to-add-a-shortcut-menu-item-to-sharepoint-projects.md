---
title: "Postupy: Přidání položky místní nabídky do projektů služby SharePoint | Microsoft Docs"
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
- projects [SharePoint development in Visual Studio], extending
- SharePoint development in Visual Studio, extending projects
- SharePoint projects, extending
ms.assetid: bb251fe9-f1bf-4ddd-9359-4b7f78fbd50f
caps.latest.revision: "9"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 9427d2307a9d9726c2df1032410168c3b5cf1cc8
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-a-shortcut-menu-item-to-sharepoint-projects"></a>Postupy: Přidání položky místní nabídky do projektů služby SharePoint
  Přidáním položky místní nabídky do žádného projektu služby SharePoint. Položky nabídky se zobrazí, když uživatel klikne pravým tlačítkem myši uzel projektu v **Průzkumníku řešení**.  
  
 Následující postup předpokládá, že jste již vytvořili rozšíření projektu. Další informace najdete v tématu [postupy: vytváření rozšíření projektu služby SharePoint](../sharepoint/how-to-create-a-sharepoint-project-extension.md).  
  
### <a name="to-add-a-shortcut-menu-item-to-sharepoint-projects"></a>Přidání položky místní nabídky do projektů služby SharePoint  
  
1.  V <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectExtension.Initialize%2A> metodu vaše <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectExtension> implementace, popisovač <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectEvents.ProjectMenuItemsRequested> události *projectService* parametr.  
  
2.  Ve vaší obslužné rutiny události pro <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectEvents.ProjectMenuItemsRequested> událostí, přidejte nový <xref:Microsoft.VisualStudio.SharePoint.IMenuItem> do objektu <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectMenuItemsRequestedEventArgs.ActionMenuItems%2A> nebo <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectMenuItemsRequestedEventArgs.AddMenuItems%2A> kolekce parametru argumentů události.  
  
3.  V <xref:Microsoft.VisualStudio.SharePoint.IMenuItem.Click> obslužné rutiny události pro nové <xref:Microsoft.VisualStudio.SharePoint.IMenuItem> objektu, provádět úlohy, kterou chcete spustit, když uživatel klikne vaší položky místní nabídky.  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu ukazuje, jak přidání položky místní nabídky do uzlů projektu služby SharePoint v **Průzkumníku řešení**. Když uživatel klikne pravým tlačítkem myši uzel projektu a klikne **zapsat zprávu do okna výstupu** položky nabídky, Visual Studio zobrazí zprávu v **výstup** okno. Tento příklad používá projektu služby SharePoint k zobrazení zprávy. Další informace najdete v tématu [pomocí projektu služby SharePoint](../sharepoint/using-the-sharepoint-project-service.md).  
  
 [!code-csharp[SPExtensibility.ProjectExtension.Menu#1](../sharepoint/codesnippet/CSharp/projectmenu/extension/projectitemextensionmenu.cs#1)]
 [!code-vb[SPExtensibility.ProjectExtension.Menu#1](../sharepoint/codesnippet/VisualBasic/projectmenu/extension/projectitemextensionmenu.vb#1)]  
  
## <a name="compiling-the-code"></a>Probíhá kompilace kódu  
 Tento příklad vyžaduje projektu knihovny tříd s odkazy na následující:  
  
-   Microsoft.VisualStudio.SharePoint  
  
-   System.ComponentModel.Composition  
  
## <a name="deploying-the-extension"></a>Nasazení rozšíření  
 Chcete-li nasadit rozšíření, vytvořte [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] balíček rozšíření (VSIX) pro sestavení a všechny další soubory, které chcete distribuovat s rozšířením. Další informace najdete v tématu [nasazení rozšíření pro nástroje služby SharePoint v sadě Visual Studio](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md).  
  
## <a name="see-also"></a>Viz také  
 [Rozšíření projektů SharePoint](../sharepoint/extending-sharepoint-projects.md)   
 [Postupy: vytváření rozšíření projektu SharePoint](../sharepoint/how-to-create-a-sharepoint-project-extension.md)   
 [Postupy: Přidání vlastnosti do projektů služby SharePoint](../sharepoint/how-to-add-a-property-to-sharepoint-projects.md)  
  
  