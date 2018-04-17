---
title: 'Postupy: přidání oblasti formuláře do projektu doplňku aplikace Outlook | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- VSTO.NewFormRegionWizard.Page1
- VSTO.NewFormRegionWizard.Page3
- VSTO.NewFormRegionWizard.Page2
- VSTO.NewFormRegionWizard.Page0
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- form regions [Office development in Visual Studio], adding
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: b8a02070bf76a1c4220c56afc397abb3b7fd3e1b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-add-a-form-region-to-an-outlook-add-in-project"></a>Postupy: Přidání oblasti formuláře do projektu doplňku pro Outlook
  Vytvoření rozšíření pomocí formuláře aplikace Microsoft Office Outlook standardní nebo vlastní oblasti formuláře **nové oblasti formuláře aplikace Outlook** průvodce. Můžete vytvořit nové oblasti formuláře a návrh uživatelského rozhraní v sadě Visual Studio, nebo můžete importovat oblasti formuláře, který byl navržen v aplikaci Outlook a přidejte kód jazyka Visual Basic nebo C#.  
  
 Pokud máte oblasti formuláře aplikace Outlook, který jste použili v jiném projektu aplikace Outlook, můžete opakovaně použít jej v aktuálním projektu doplňku VSTO pro Outlook pomocí **přidat existující položku** dialogové okno. Další informace najdete v tématu [vytváření oblastí formulářů aplikace Outlook](../vsto/creating-outlook-form-regions.md).  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
### <a name="to-add-a-new-form-region-to-an-outlook-project"></a>Chcete-li přidat nové oblasti formuláře do projektu aplikace Outlook  
  
1.  Otevření nebo vytvoření projektu doplňku VSTO v Outlooku v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]. Další informace najdete v tématu [postupy: vytváření projektů Office v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
2.  V **Průzkumníku**, vyberte uzel projektu doplňku VSTO v Outlooku.  
  
3.  Na **projektu** nabídky, klikněte na tlačítko **přidat novou položku**.  
  
4.  V **přidat novou položku** dialogové okno, vyberte **oblasti formuláře aplikace Outlook**.  
  
5.  Zadejte název oblasti formuláře v **název** pole a pak klikněte na **přidat**.  
  
     **Oblasti formuláře NewOutlook** spustí se průvodce.  
  
6.  Na **vyberte způsob vytvoření oblasti formuláře** vyberte, jestli chcete návrh oblasti formuláře pomocí přetahování spravovaných ovládacích prvků do vizuálního návrháře nebo import oblasti formuláře, který byl navržen v aplikaci Outlook.  
  
    > [!NOTE]  
    >  Pokud si zvolíte import oblasti formuláře, který byl navržen v aplikaci Outlook, je nutné zadat umístění souboru úložiště formuláře aplikace Outlook (.ofs). Spravované ovládací prvky nelze přidat do oblasti formuláře navržené v aplikaci Outlook; můžete přidat pouze kódu existující uživatelské rozhraní. Další informace najdete v tématu [vytváření oblastí formulářů aplikace Outlook](../vsto/creating-outlook-form-regions.md).  
  
7.  Na **vyberte typ oblasti formuláře, které chcete vytvořit** projděte typy oblasti formuláře a vyberte jeden a pak klikněte na tlačítko **Další**. Další informace o typech oblasti formuláře najdete v tématu [vytváření oblastí formulářů aplikace Outlook](../vsto/creating-outlook-form-regions.md).  
  
8.  Na **zadejte popisný text a vybrat vaše předvolby zobrazení** stránky v **název** pole, zadejte název oblasti formuláře. Pro nahrazení a nahradit všechny formuláře typy oblastí **název** a **popis** polí jsou také k dispozici.  
  
     Informace o kde název, název a popis se zobrazí v aplikaci Outlook při nasazování oblasti formuláře najdete v tématu [vytváření oblastí formulářů aplikace Outlook](../vsto/creating-outlook-form-regions.md).  
  
9. Vyberte jeden nebo více režimů zobrazení, ve kterých chcete oblasti formuláře se objeví.  
  
     Všechny typy oblasti formuláře se mohou objevit v inspektoři, v nové režimu (pro vytváření položek) a (pro zobrazení položky) v režimu čtení. V podokně čtení může zobrazit i přiléhající k nahrazení typy a nahradit všechny formuláře oblast.  
  
10. Klikněte na tlačítko **Další**.  
  
11. Na **identifikovat zpráva třídy, které se zobrazí tato oblasti formuláře** vyberte standardní tříd zpráv aplikace Outlook nebo zadejte názvy jednu nebo více tříd vlastní zprávu a potom klikněte na **Dokončit**. Další informace najdete v tématu [přidružení oblasti formuláře k třídě zpráv aplikace Outlook](../vsto/associating-a-form-region-with-an-outlook-message-class.md).  
  
## <a name="see-also"></a>Viz také  
 [Přístup k oblasti formuláře za běhu](../vsto/accessing-a-form-region-at-run-time.md)   
 [Řešení pro aplikaci Outlook](../vsto/outlook-solutions.md)   
 [Vytváření oblastí formulářů aplikace Outlook](../vsto/creating-outlook-form-regions.md)   
 [Pokyny pro vytváření oblastí formulářů aplikace Outlook](../vsto/guidelines-for-creating-outlook-form-regions.md)   
 [Postupy: Návrh oblasti formuláře aplikace Outlook](../vsto/walkthrough-designing-an-outlook-form-region.md)   
 [Návod: Import oblasti formuláře navržené v aplikaci Outlook](../vsto/walkthrough-importing-a-form-region-that-is-designed-in-outlook.md)   
 [Vlastní akce v oblastech formulářů aplikace Outlook](../vsto/custom-actions-in-outlook-form-regions.md)  
  
  