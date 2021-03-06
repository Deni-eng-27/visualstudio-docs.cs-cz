---
title: Přidat položku místní nabídky do rozšíření položky projektu SharePoint
titleSuffix: ''
ms.date: 02/02/2017
ms.topic: how-to
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- project items [SharePoint development in Visual Studio], extending
- SharePoint project items, extending
- SharePoint development in Visual Studio, extending project items
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: d3c0627849df12b98ddc16f54317faf952cb41f6
ms.sourcegitcommit: 9d2829dc30b6917e89762d602022915f1ca49089
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/30/2020
ms.locfileid: "91585859"
---
# <a name="how-to-add-a-shortcut-menu-item-to-a-sharepoint-project-item-extension"></a>Postupy: Přidání položky místní nabídky do rozšíření položky projektu služby SharePoint
  Můžete přidat položku místní nabídky do existující položky projektu služby SharePoint pomocí rozšíření položky projektu. Položka nabídky se zobrazí, když uživatel klikne pravým tlačítkem myši na položku projektu v **Průzkumník řešení**.

 Následující postup předpokládá, že jste již vytvořili rozšíření položky projektu. Další informace naleznete v tématu [Postupy: Vytvoření rozšíření položky projektu služby SharePoint](../sharepoint/how-to-create-a-sharepoint-project-item-extension.md).

### <a name="to-add-a-shortcut-menu-item-in-a-project-item-extension"></a>Přidání položky místní nabídky v rozšíření položky projektu

1. V <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeExtension.Initialize%2A> metodě vaší <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeExtension> implementace zpracujte <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemMenuItemsRequested> událost parametru *projectItemType* .

2. V obslužné rutině události pro <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemMenuItemsRequested> událost přidejte nový <xref:Microsoft.VisualStudio.SharePoint.IMenuItem> objekt do <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectItemMenuItemsRequestedEventArgs.ViewMenuItems%2A> kolekce nebo v <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectItemMenuItemsRequestedEventArgs.AddMenuItems%2A> parametru argumenty události.

3. V <xref:Microsoft.VisualStudio.SharePoint.IMenuItem.Click> obslužné rutině události pro nový <xref:Microsoft.VisualStudio.SharePoint.IMenuItem> objekt proveďte úkoly, které chcete spustit, když uživatel klikne na položku místní nabídky.

## <a name="example"></a>Příklad
 Následující příklad kódu ukazuje, jak přidat položku místní nabídky do položky projektu přijímače událostí. Když uživatel klikne pravým tlačítkem myši na položku projektu v **Průzkumník řešení** a klikne na položku nabídky **napsat zprávu pro okno výstup** , Visual Studio zobrazí zprávu v okně **výstup** .

 [!code-vb[SPExtensibility.ProjectItemExtension.MenuAndProperty#1](../sharepoint/codesnippet/VisualBasic/projectitemmenuandproperty/extension/projectitemextensionmenu.vb#1)]
 [!code-csharp[SPExtensibility.ProjectItemExtension.MenuAndProperty#1](../sharepoint/codesnippet/CSharp/projectitemmenuandproperty/extension/projectitemextensionmenu.cs#1)]

 Tento příklad používá službu projektu SharePoint k zápisu zprávy do okna **výstup** . Další informace naleznete v tématu [použití služby projektu služby SharePoint](../sharepoint/using-the-sharepoint-project-service.md).

## <a name="compile-the-code"></a>Kompilovat kód
 Tento příklad vyžaduje projekt knihovny tříd s odkazy na následující sestavení:

- Microsoft. VisualStudio. SharePoint

- System. ComponentModel. složení

## <a name="deploy-the-extension"></a>Nasazení rozšíření
 Chcete-li nasadit rozšíření, vytvořte [!include[vsprvs](../sharepoint/includes/vsprvs-md.md)] balíček rozšíření (VSIX) pro sestavení a všechny další soubory, které chcete distribuovat s rozšířením. Další informace naleznete v tématu [nasazení rozšíření pro nástroje služby SharePoint v aplikaci Visual Studio](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md).

## <a name="see-also"></a>Viz také
- [Postupy: Vytvoření rozšíření položky projektu služby SharePoint](../sharepoint/how-to-create-a-sharepoint-project-item-extension.md)
- [Postupy: Přidání vlastnosti do rozšíření položky projektu služby SharePoint](../sharepoint/how-to-add-a-property-to-a-sharepoint-project-item-extension.md)
- [Rozšiřování položek projektu služby SharePoint](../sharepoint/extending-sharepoint-project-items.md)
- [Návod: rozšiřování typu položky projektu služby SharePoint](../sharepoint/walkthrough-extending-a-sharepoint-project-item-type.md)
