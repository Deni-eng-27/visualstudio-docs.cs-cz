---
title: "Přístup k pásu karet za běhu | Microsoft Docs"
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
- Globals class, Ribbon
- Ribbon [Office development in Visual Studio], accessing
- RibbonManager class
ms.assetid: 8a7c7c6d-1a18-4d6b-98ee-e483d41f0cd8
caps.latest.revision: "23"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: f69818d2e7c1b6ef2babd651247fe81709b80097
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="accessing-the-ribbon-at-run-time"></a>Přístup k pásu karet za běhu
  Můžete napsat kód pro zobrazení, skrytí a upravit na pásu karet a povolit uživatelům spustit kód z ovládacích prvků v vlastního podokna úloh, podokna akce nebo oblasti formuláře aplikace Outlook.  
  
 Máte přístup k pásu karet pomocí `Globals` třídy. Pro aplikaci Outlook projekty dostanete pásů karet, které se zobrazují v konkrétní okno Kontrola aplikace Outlook nebo v Průzkumníku aplikace Outlook.  
  
 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]  
  
## <a name="accessing-the-ribbon-by-using-the-globals-class"></a>Přístup k pásu karet pomocí Globals – třída  
 Můžete použít `Globals` třídy pro přístup k pásu karet v projektech na úrovni dokumentu nebo v projektu doplňku VSTO z libovolného místa v projektu.  
  
 Další informace o `Globals` třídy najdete v tématu [globální přístup k objektům v projektech Office](../vsto/global-access-to-objects-in-office-projects.md).  
  
 Následující příklad používá `Globals` třídy pro přístup k vlastní pás karet s názvem `Ribbon1` a nastavit text, který se zobrazí na pole se seznamem na pásu karet `Hello World`.  
  
 [!code-vb[Trin_Outlook_FR_Access#4](../vsto/codesnippet/VisualBasic/Trin_Outlook_FR_Access_O12/ThisAddIn.vb#4)]
 [!code-csharp[Trin_Outlook_FR_Access#4](../vsto/codesnippet/CSharp/Trin_Outlook_FR_Access_O12/ThisAddIn.cs#4)]  
  
## <a name="accessing-a-collection-of-ribbons-that-appear-in-a-specific-outlook-inspector-window"></a>Přístup ke kolekci pásů karet, které se zobrazují v okně kontroly konkrétní aplikace  
 Dostanete kolekce pásů karet, které se zobrazují v aplikaci Outlook *inspektoři*. Kontrolor je okno, které se otevře v aplikaci Outlook, když uživatelé provádět určité úlohy, jako je například vytváření e-mailových zpráv. Chcete-li získat přístup k pásu karet okně kontroly, volejte `Ribbons` vlastnost `Globals` třídy a předat <xref:Microsoft.Office.Interop.Outlook.Inspector> objekt, který představuje funkci Kontrola.  
  
 Následující příklad načte kolekci pásu karet Inspector, který má právě fokus. Tento příklad následně přistupuje k pásu karet s názvem `Ribbon1` a nastaví text, který se zobrazí na pole se seznamem na pásu karet `Hello World`.  
  
 [!code-vb[Trin_Outlook_FR_Access#5](../vsto/codesnippet/VisualBasic/Trin_Outlook_FR_Access_O12/ThisAddIn.vb#5)]
 [!code-csharp[Trin_Outlook_FR_Access#5](../vsto/codesnippet/CSharp/Trin_Outlook_FR_Access_O12/ThisAddIn.cs#5)]  
  
## <a name="accessing-a-collection-of-ribbons-that-appear-for-a-specific-outlook-explorer"></a>Přístup ke kolekci pásů karet, které se zobrazují pro konkrétní aplikace Outlook Explorer  
 Dostanete kolekce pásů karet, které se zobrazují v aplikace Outlook *Explorer*. Je Explorer hlavní aplikace uživatelské rozhraní (UI) pro instance aplikace Outlook. Chcete-li získat přístup k pásu karet okno Průzkumníka, zavolejte `Ribbons` vlastnost `Globals` třídy a předat <xref:Microsoft.Office.Interop.Outlook.Explorer> objekt, který reprezentuje Průzkumníku.  
  
 Následující příklad načte kolekci pásu karet Explorer, který má právě fokus. Tento příklad následně přistupuje k pásu karet s názvem `Ribbon1` a nastaví text, který se zobrazí na pole se seznamem na pásu karet `Hello World`.  
  
 [!code-vb[Trin_Outlook_FR_Access#6](../vsto/codesnippet/VisualBasic/Trin_Outlook_FR_Access_O12/ThisAddIn.vb#6)]
 [!code-csharp[Trin_Outlook_FR_Access#6](../vsto/codesnippet/CSharp/Trin_Outlook_FR_Access_O12/ThisAddIn.cs#6)]  
  
## <a name="see-also"></a>Viz také  
 [Přehled pásu karet](../vsto/ribbon-overview.md)   
 [Návrhář pásu karet](../vsto/ribbon-designer.md)   
 [Kódu XML pásu karet](../vsto/ribbon-xml.md)   
 [Přehled modelu objektů pásu karet](../vsto/ribbon-object-model-overview.md)   
 [Návod: Vytvoření vlastní karty pomocí Návrháře pásu karet](../vsto/walkthrough-creating-a-custom-tab-by-using-the-ribbon-designer.md)   
 [Návod: Aktualizace ovládacích prvků na pásu karet za běhu](../vsto/walkthrough-updating-the-controls-on-a-ribbon-at-run-time.md)   
 [Přizpůsobení pásu karet pro aplikaci Outlook](../vsto/customizing-a-ribbon-for-outlook.md)   
 [Přístup k oblasti formuláře za běhu](../vsto/accessing-a-form-region-at-run-time.md)  
  
  