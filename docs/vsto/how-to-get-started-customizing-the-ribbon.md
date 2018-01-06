---
title: "Postupy: Začínáme s přizpůsobením pásu karet | Microsoft Docs"
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
- custom Ribbon, adding Ribbon to project
- Ribbon [Office development in Visual Studio], adding
- Ribbon [Office development in Visual Studio], customizing
- customizing the Ribbon, adding Ribbon to project
ms.assetid: 9eb6b8b3-1842-4cb3-8229-273ce35c64fb
caps.latest.revision: "22"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 8ede4048722fd18f62fe4d0bbf19ac75995cb99e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-get-started-customizing-the-ribbon"></a>Postupy: Začínáme s přizpůsobením pásu karet
  Chcete-li přizpůsobit na pásu karet z aplikace Microsoft Office, přidejte **pásu karet (vizuálního návrháře)** nebo **pásu karet (XML)** položku do projektu Office.  
  
 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]  
  
### <a name="to-add-a-ribbon-to-a-project"></a>Chcete-li přidat pásu karet do projektu  
  
1.  Na **projektu** nabídky, klikněte na tlačítko **přidat novou položku**.  
  
2.  V **přidat novou položku** dialogové okno, vyberte **pásu karet (vizuálního návrháře)** nebo **pásu karet (XML)**. Další informace o těchto šablon najdete v tématu [přehled pásu karet](../vsto/ribbon-overview.md).  
  
3.  V **název** zadejte název pro položku pásu karet.  
  
     Názvy nesmí obsahovat následující znaky:  
  
    -   Křížku (#)  
  
    -   Procent (%)  
  
    -   Ampersand (&)  
  
    -   Znak hvězdičky (*)  
  
    -   Svislé čáry (|)  
  
    -   Zpětné lomítko (\\)  
  
    -   Dvojtečkou (:)  
  
    -   Dvojité uvozovky (")  
  
    -   Menší než (\<)  
  
    -   Větší než (>)  
  
    -   Otazník (?)  
  
    -   Předat dál lomítko (/)  
  
    -   Počáteční nebo koncové mezery ("")  
  
    -   Názvy vyhrazené pro Windows nebo DOS například ("nul", "aux", "con", "com1", "lpt1" a tak dále)  
  
4.  Click **OK**.  
  
 Položka pásu karet se zobrazí v **Průzkumníku řešení**. Informace o dalších krocích, najdete v tématu [přehled pásu karet](../vsto/ribbon-overview.md).  
  
## <a name="see-also"></a>Viz také  
 [Přístup k pásu karet za běhu](../vsto/accessing-the-ribbon-at-run-time.md)   
 [Návrhář pásu karet](../vsto/ribbon-designer.md)   
 [Kódu XML pásu karet](../vsto/ribbon-xml.md)   
 [Návod: Vytvoření vlastní karty pomocí Návrháře pásu karet](../vsto/walkthrough-creating-a-custom-tab-by-using-the-ribbon-designer.md)   
 [Návod: Vytvoření vlastní karty pomocí kódu XML pásu karet](../vsto/walkthrough-creating-a-custom-tab-by-using-ribbon-xml.md)  
  
  