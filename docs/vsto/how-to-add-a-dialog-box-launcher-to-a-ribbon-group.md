---
title: "Postupy: Přidání Spouštěče dialogového okna do skupiny pásu karet | Microsoft Docs"
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
- dialog box launcher [Office development in Visual Studio]
- Ribbon [Office development in Visual Studio], dialog box launcher
ms.assetid: 5972664f-4e37-4dc6-90d0-69cedd057e60
caps.latest.revision: "19"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: f9b9b3500b833b8ecf56d66d036f8284484b6600
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-a-dialog-box-launcher-to-a-ribbon-group"></a>Postupy: Přidání spouštěče dialogového okna do skupiny pásu karet
  Spouštěče dialogového okna můžete přidat na žádnou skupinu na pásu karet. Spouštěče dialogového okna je malý ikonu, která se zobrazí ve skupině. Uživatelé kliknou na tuto ikonu otevřete související dialogových oken nebo podokna úloh, které poskytují další možnosti, které se vztahují ke skupině.  
  
 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]  
  
### <a name="to-add-a-dialog-box-launcher-to-a-ribbon-group"></a>Přidání Spouštěče dialogového okna do skupiny pásu karet  
  
1.  Vyberte soubor kódu pásu karet (soubor vb nebo .cs) v **Průzkumníku řešení**.  
  
2.  Na **zobrazení** nabídky, klikněte na tlačítko **Návrhář**.  
  
3.  Návrhář pásu karet klikněte pravým tlačítkem na všechny skupiny a pak klikněte na **přidat DialogBoxLauncher**.  
  
     Přidejte kód, který <xref:Microsoft.Office.Tools.Ribbon.RibbonGroup.DialogLauncherClick> událostí skupiny otevřete vlastní nebo integrované dialogové okno.  
  
## <a name="see-also"></a>Viz také  
 [Přehled pásu karet](../vsto/ribbon-overview.md)   
 [Přístup k pásu karet za běhu](../vsto/accessing-the-ribbon-at-run-time.md)   
 [Office Ukázky a návody vývoje](../vsto/office-development-samples-and-walkthroughs.md)   
 [Návrhář pásu karet](../vsto/ribbon-designer.md)   
 [Přehled modelu objektů pásu karet](../vsto/ribbon-object-model-overview.md)   
 [Kódu XML pásu karet](../vsto/ribbon-xml.md)   
 [Postupy: Export pásu karet z Návrháře pásu karet do kódu XML pásu karet](../vsto/how-to-export-a-ribbon-from-the-ribbon-designer-to-ribbon-xml.md)   
 [Postupy: Změna polohy karty na pásu karet](../vsto/how-to-change-the-position-of-a-tab-on-the-ribbon.md)   
 [Postupy: Přizpůsobení předdefinované karty](../vsto/how-to-customize-a-built-in-tab.md)   
 [Postupy: Přidání ovládacích prvků do zobrazení Backstage](../vsto/how-to-add-controls-to-the-backstage-view.md)   
 [Přizpůsobení pásu karet pro aplikaci Outlook](../vsto/customizing-a-ribbon-for-outlook.md)   
 [Postupy: Začínáme s přizpůsobením pásu karet](../vsto/how-to-get-started-customizing-the-ribbon.md)   
 [Postupy: Zobrazit chyby doplňku uživatelského rozhraní](../vsto/how-to-show-add-in-user-interface-errors.md)   
 [Návod: Vytvoření vlastní karty pomocí Návrháře pásu karet](../vsto/walkthrough-creating-a-custom-tab-by-using-the-ribbon-designer.md)   
 [Návod: Aktualizace ovládacích prvků na pásu karet za běhu](../vsto/walkthrough-updating-the-controls-on-a-ribbon-at-run-time.md)   
 [Návod: Vytvoření vlastní karty pomocí kódu XML pásu karet](../vsto/walkthrough-creating-a-custom-tab-by-using-ribbon-xml.md)  
  
  