---
title: 'Postupy: Vytvoření stránky aplikace | Dokumentace Microsoftu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- application pages [SharePoint development in Visual Studio], adding
- application pages [SharePoint development in Visual Studio], creating
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: fb5c4d7497525706384ced52caae1ba8e02f3e23
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60063020"
---
# <a name="how-to-create-an-application-page"></a>Postupy: Vytvoření stránky aplikace
  Můžete vytvořit webovou stránku ASP.NET pro jeden nebo více webů služby SharePoint. Ve službě SharePoint se nazývají tyto stránky stránky aplikace. Na rozdíl od lokality stránky stránky aplikace obsahuje kód, který spouští za bránou stránky. Další informace najdete v tématu [vytváření stránek aplikací pro SharePoint](../sharepoint/creating-application-pages-for-sharepoint.md).

### <a name="to-create-an-application-page"></a>Vytvoření stránky aplikace

1. V aplikaci Visual Studio otevřete nebo vytvořte projekt služby SharePoint.

     Další informace najdete v tématu [SharePoint šablony položek projektu a projekt](../sharepoint/sharepoint-project-and-project-item-templates.md).

2. V **Průzkumníka řešení**, zvolte uzel projektu.

3. V panelu nabídky zvolte **projektu** > **přidat novou položku**.

4. V **přidat novou položku** dialogového okna rozbalte **SharePoint** uzel a klikněte na tlačítko **2010** položky.

5. V seznamu šablon služby SharePoint, zvolte **stránky aplikace**.

6. V **název** pole, zadejte název pro stránku aplikace a klikněte na tlačítko **přidat** tlačítko.

     Aplikace Visual Studio přidá do projektu několik složek a souborů. Další informace o těchto souborech najdete v tématu [vytváření stránek aplikací pro SharePoint](../sharepoint/creating-application-pages-for-sharepoint.md).

     V **zdroj** se zobrazení návrháře Visual Web Developer souboru stránky ASP.NET. Stránky můžete navrhnout přidáním ovládacích prvků **nástrojů** a jejich uvedení na obsahu zástupné symboly. Další informace najdete v tématu [zobrazení zdrojového kódu, webové stránky návrháře](/previous-versions/aspnet/ms178154\(v\=vs.100\)).

7. Pokud chcete zpracovat události ovládacího prvku, přidejte kód do souboru kódu stránky aplikace.

     Soubor kódu se zobrazí v případě rozbalte uzel pro stránkovací soubor ASP.NET a má *.cs* nebo *.vb* rozšíření, v závislosti na jazyce projektu. Začátku do konce příklad toho, jak vytvořit stránku aplikace, najdete v části [názorný postup: Vytvoření stránky aplikace služby SharePoint](../sharepoint/walkthrough-creating-a-sharepoint-application-page.md).

## <a name="see-also"></a>Viz také:
- [Vytváření stránek aplikací pro SharePoint](../sharepoint/creating-application-pages-for-sharepoint.md)
- [Návod: Vytvoření stránky aplikace služby SharePoint](../sharepoint/walkthrough-creating-a-sharepoint-application-page.md)
