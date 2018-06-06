---
title: Použití ovládacích prvků WPF v řešeních pro systém Office
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- WPF [Office development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 87305902c80d9848df63d2c8bd9f431fd93a5508
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/05/2018
ms.locfileid: "34767592"
---
# <a name="use-wpf-controls-in-office-solutions"></a>Použití ovládacích prvků WPF v řešeních pro systém Office
  I když řešení vytvořená pomocí nástrojů pro vývoj pro Office v sadě Visual Studio jsou navrženy pro práci s přímo s Windows Forms – ovládací prvky, které můžete použít ovládacích prvků WPF v řešeních. Windows Presentation Foundation (WPF) představuje alternativu k Windows Forms pro návrh uživatelského rozhraní. WPF pomocí značek jazyka nazývaného rozšiřitelné aplikace Markup Language (XAML) poskytuje nové techniky zařadit uživatelského rozhraní, média a dokumenty. Další informace najdete v tématu [Úvod k použití WPF v sadě Visual Studio 2015](/dotnet/framework/wpf/getting-started/introduction-to-wpf-in-vs).  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
 Libovolný element uživatelského rozhraní, který může hostovat ovládací prvky Windows Forms v řešení Office může hostovat ovládacích prvků WPF. Mezi ně patří následující prvky:  
  
-   Dokumenty a listy v přizpůsobeních na úrovni dokumentu.  
  
-   Podokna akcí v přizpůsobeních na úrovni dokumentu.  
  
-   Vlastní podokna úloh v doplňcích VSTO.  
  
-   Oblasti formuláře v doplňcích VSTO pro Outlook.  
  
## <a name="add-wpf-controls-to-office-projects-at-design-time"></a>Přidání ovládacích prvků WPF do projektů Office v době návrhu  
 Nelze přidat ovládacích prvků WPF přímo k elementům uživatelského rozhraní v řešeních pro systém Office. Místo toho přidejte **uživatelského ovládacího prvku (WPF)** položku do projektu a používejte ho jako návrhové ploše pro ovládacích prvků WPF. Potom můžete přidáte uživatelský ovládací prvek WPF do elementu uživatelského rozhraní v projektu.  
  
### <a name="to-add-wpf-controls-to-an-actions-pane-custom-task-pane-or-form-region"></a>Přidání ovládacích prvků WPF do podokna akce, vlastního podokna úloh nebo oblasti formuláře  
  
1.  Otevřete projekt, do které chcete přidat vlastního podokna úloh, podokna akcí nebo oblasti formuláře.  
  
2.  Přidat **uživatelského ovládacího prvku (WPF)** položku do projektu.  
  
3.  Z **sada nástrojů**, přidání ovládacích prvků WPF na plochu návrháře ovládací prvek WPF uživatele.  
  
     Ve výchozím nastavení, pokud Návrháře WPF uživatele řízení je otevřený **sada nástrojů** obsahuje pouze ovládacích prvků WPF.  
  
4.  Sestavte projekt.  
  
5.  Přidání podokna akcí, oblasti formuláře nebo vlastního podokna úloh do projektu:  
  
    -   Oblasti formuláře, přidejte **oblasti formuláře aplikace Outlook** položku do projektu. Další informace najdete v tématu [postupy: přidání oblasti formuláře do projektu doplněk aplikace Outlook](../vsto/how-to-add-a-form-region-to-an-outlook-add-in-project.md).  
  
    -   Podokna akcí, přidejte **ovládací prvek podokna akce** nebo **uživatelský ovládací prvek** položku do projektu. Další informace najdete v tématu [postupy: Přidání podokna akcí do dokumentů aplikace Word nebo sešitů aplikace Excel](../vsto/how-to-add-an-actions-pane-to-word-documents-or-excel-workbooks.md) a [postupy: Přidání podokna akcí do dokumentů aplikace Word nebo sešitů aplikace Excel](../vsto/how-to-add-an-actions-pane-to-word-documents-or-excel-workbooks.md).  
  
    -   Vlastní podokna úloh, přidejte **uživatelský ovládací prvek** položku do projektu. Další informace najdete v tématu [postupy: Přidání vlastního podokna úloh do aplikace](../vsto/how-to-add-a-custom-task-pane-to-an-application.md).  
  
6.  Z *ProjectName* **uživatelských ovládacích prvků WPF** kartě **sada nástrojů**, přetáhněte uživatelský ovládací prvek WPF designer pro podokna akce, oblasti formuláře nebo vlastního podokna úloh.  
  
     Visual Studio automaticky vytvoří <xref:System.Windows.Forms.Integration.ElementHost> objekt, který je hostitelem uživatelský ovládací prvek WPF element uživatelského rozhraní.  
  
7.  Znovu sestavte projekt.  
  
#### <a name="to-add-wpf-controls-to-a-document-or-worksheet-in-a-document-level-project"></a>Přidání ovládacích prvků WPF k dokumentu nebo sešitu v projektech na úrovni dokumentu  
  
1.  Otevřete projekt na úrovni dokumentu pro Word či Excel.  
  
2.  Přidat **uživatelského ovládacího prvku (WPF)** položku do projektu.  
  
3.  Z **sada nástrojů**, přidání ovládacích prvků WPF na plochu návrháře ovládací prvek WPF uživatele.  
  
4.  Sestavte projekt.  
  
5.  Přidat **uživatelský ovládací prvek** položky (to znamená, uživatel ovládacího prvku Windows Forms) k projektu.  
  
6.  Otevřete návrháře uživatelského ovládacího prvku Windows Forms.  
  
7.  Z *ProjectName* **uživatelských ovládacích prvků WPF** kartě **sada nástrojů**, přetáhněte uživatelský ovládací prvek WPF do návrháře.  
  
     Visual Studio automaticky vytvoří <xref:System.Windows.Forms.Integration.ElementHost> objekt, který je hostitelem uživatelský ovládací prvek WPF v ovládacím prvku Windows Forms uživatele.  
  
8.  Napište kód, který prostřednictvím kódu programu přidá uživatelského ovládacího prvku Windows Forms k dokumentu nebo sešitu. Další informace najdete v tématu [přidání ovládacích prvků do dokumentů Office za běhu](../vsto/adding-controls-to-office-documents-at-run-time.md).  
  
    > [!NOTE]  
    >  Nelze přetáhnout uživatelského ovládacího prvku Windows Forms k dokumentu nebo listu v návrháři.  
  
9. Znovu sestavte projekt.  
  
## <a name="host-wpf-controls-by-using-the-elementhost-class"></a>Hostitelské ovládací prvky WPF pomocí elementhost – třída  
 Visual Studio poskytuje funkce, které vám pomohou používat ovládací prvky Windows Forms v řešeních pro systém Office, ale neposkytuje podobné funkce pro ovládacích prvků WPF. Například přidáním ovládací prvky Windows Forms k dokumentům a listy v době návrhu tak, že přetáhnete ovládacích prvků z **sada nástrojů**, nebo za běhu pomocí pomocné metody. Tyto nástroje však nejsou k dispozici pro ovládacích prvků WPF.  
  
 Řídí použití WPF <xref:System.Windows.Forms.Integration.ElementHost> třída jako vrstva integrace mezi ovládacího prvku Windows Forms nebo formuláře a ovládacích prvků WPF. Při přidání ovládacích prvků WPF k řešení v době návrhu, Visual Studio automaticky generuje <xref:System.Windows.Forms.Integration.ElementHost> objektu za vás.  
  
## <a name="wpf-resources"></a>Prostředky grafického subsystému WPF  
 Další informace o architektuře a problémy návrhu pro hostování ovládacích prvků WPF ve formulářích a ovládací prvky Windows Forms najdete v následujících tématech:  
  
-   [Windows Forms a WPF vstupní architektura interoperability](/dotnet/framework/wpf/advanced/windows-forms-and-wpf-interoperability-input-architecture)  
  
-   [Windows Forms a WPF mapování vlastností](/dotnet/framework/wpf/advanced/windows-forms-and-wpf-property-mapping)  
  
-   [Vzájemná spolupráce WPF a Windows Forms](/dotnet/framework/wpf/advanced/wpf-and-windows-forms-interoperation)  
  
-   [Ovládací prvky Windows Forms – ovládací prvky a ekvivalentní WPF](/dotnet/framework/wpf/advanced/windows-forms-controls-and-equivalent-wpf-controls)  
  
 Další informace o přidávání ovládacích prvků WPF v době návrhu pro ovládací prvky Windows Forms a formuláře v sadě Visual Studio najdete v následujících tématech:  
  
-   [Návod: Vytvoření nového obsahu WPF v rozhraní Windows Forms v době návrhu](/dotnet/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time)  
  
-   [Návod: Uspořádání obsahu WPF ve Windows Forms v době návrhu](/dotnet/framework/winforms/advanced/walkthrough-arranging-wpf-content-on-windows-forms-at-design-time)  
  
-   [Návod: Stylu obsahu WPF](/dotnet/framework/winforms/advanced/walkthrough-styling-wpf-content)  
  
## <a name="see-also"></a>Viz také:  
 [Přizpůsobení uživatelského rozhraní sady Office](../vsto/office-ui-customization.md)   
 [Ovládací prvky Windows Forms na přehled dokumenty sady Office](../vsto/windows-forms-controls-on-office-documents-overview.md)   
 [Přehled podokna akcí](../vsto/actions-pane-overview.md)   
 [Vlastní podokna úloh](../vsto/custom-task-panes.md)   
 [Vytváření oblastí formulářů aplikace Outlook](../vsto/creating-outlook-form-regions.md)   
 [Postupy: Přidání podokna akcí do dokumentů aplikace Word nebo sešitů aplikace Excel](../vsto/how-to-add-an-actions-pane-to-word-documents-or-excel-workbooks.md)   
 [Postupy: Přidání podokna akcí do dokumentů aplikace Word nebo sešitů aplikace Excel](../vsto/how-to-add-an-actions-pane-to-word-documents-or-excel-workbooks.md)   
 [Postupy: Přidání vlastního podokna úloh do aplikace](../vsto/how-to-add-a-custom-task-pane-to-an-application.md)   
 [Postupy: přidání oblasti formuláře do projektu doplněk aplikace Outlook](../vsto/how-to-add-a-form-region-to-an-outlook-add-in-project.md)  
  
  