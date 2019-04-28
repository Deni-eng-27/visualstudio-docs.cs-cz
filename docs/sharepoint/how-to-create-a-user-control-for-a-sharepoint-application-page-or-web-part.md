---
title: 'Postupy: Vytvoření uživatelského ovládacího prvku pro stránku aplikace služby SharePoint nebo webovou část | Dokumentace Microsoftu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- user controls [SharePoint development in Visual Studio], creating
- user controls [SharePoint development in Visual Studio], adding
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 17f8acd38df810d0ea7e5c0da2293a5de31eb281
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63446505"
---
# <a name="how-to-create-a-user-control-for-a-sharepoint-application-page-or-web-part"></a>Postupy: Vytvoření uživatelského ovládacího prvku pro části stránky nebo webové aplikace služby SharePoint
  Můžete také vytvářet vlastní uživatelské ovládací prvky, které poskytují vlastní funkce pro řešení služby SharePoint, a tyto funkce v rámci svého projektu znovu využívat. De webové části nebo do stránky aplikace lze zahrnout uživatelské ovládací prvky, přidat další ovládací prvky technologie ASP.NET, ovládací prvky služby SharePoint a definovat vlastnosti a metody pro ovládací prvek. Další informace o uživatelských ovládacích prvcích najdete v tématu [vytvořit opakovaně použitelné ovládací prvky webové části nebo stránky aplikace](../sharepoint/creating-reusable-controls-for-web-parts-or-application-pages.md) a [uživatelské ovládací prvky a ovládací prvky serveru ve službě SharePoint](https://blogs.msdn.microsoft.com/kaevans/2011/04/28/user-controls-and-server-controls-in-sharepoint/).

### <a name="to-create-a-user-control-for-sharepoint"></a>Vytvoření uživatelského ovládacího prvku služby SharePoint.

1. V aplikaci Visual Studio otevřete nebo vytvořte projekt služby SharePoint.

     Zobrazit [SharePoint šablony položek projektu a projekt](../sharepoint/sharepoint-project-and-project-item-templates.md).

2. V **Průzkumníka řešení**, zvolte uzel projektu.

3. V panelu nabídky zvolte **projektu** > **přidat novou položku**.

     **Přidat novou položku** zobrazí se dialogové okno.

4. V **nainstalováno** podokně, vyberte **Office/SharePoint** uzlu.

5. V seznamu šablon služby SharePoint, zvolte **uživatelský ovládací prvek (pouze řešení farmy)**.

    > [!NOTE]
    > Uživatelské ovládací prvky fungují pouze pro řešení farmy.

6. V **název** pole, zadejte název pro uživatelský ovládací prvek a klikněte na tlačítko **přidat** tlačítko.

     Aplikace Visual Studio přidá do projektu několik složek a souborů. Další informace o těchto souborech najdete v tématu [vytvořit opakovaně použitelné ovládací prvky webové části nebo stránky aplikace](../sharepoint/creating-reusable-controls-for-web-parts-or-application-pages.md).

     Ve výchozím souboru uživatelského ovládacího prvku se zobrazí v **zdroj** zobrazení návrháře Visual Web Developer. V tomto zobrazení lze upravit značku XML ovládacího prvku. Můžete přepnout na **návrhu** zobrazit, pokud chcete navrhnout ovládacího prvku vizuálně přetažením ovládacích prvků **nástrojů**. Zobrazit [zobrazení návrhu, Designer webových stránek](/previous-versions/aspnet/ms178149\(v\=vs.100\)).

7. Pokud chcete zpracovávat události, ke kterým došlo v ovládacím prvku, přidejte kód do souboru kódu uživatelského ovládacího prvku.

     Tento soubor se zobrazí v **Průzkumníka řešení** v souboru uživatelského ovládacího prvku a má *.cs* nebo *.vb* rozšíření, v závislosti na jazyce projektu.

## <a name="see-also"></a>Viz také:
- [Vytvoření opakovaně použitelné ovládací prvky webové části nebo stránky aplikace](../sharepoint/creating-reusable-controls-for-web-parts-or-application-pages.md)
- [Vytváření stránek aplikací pro SharePoint](../sharepoint/creating-application-pages-for-sharepoint.md)
- [Vytvoření webové části pro SharePoint](../sharepoint/creating-web-parts-for-sharepoint.md)
