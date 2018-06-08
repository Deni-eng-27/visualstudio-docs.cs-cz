---
title: 'Návod: Vytvoření vaší první Add-in VSTO pro PowerPoint'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- application-level add-ins [Office development in Visual Studio], creating your first project
- Office development in Visual Studio, creating your first project
- PowerPoint [Office development in Visual Studio], creating your first project
- add-ins [Office development in Visual Studio], creating your first project
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 0f55ebded09782f6a6ab15ec5646778cc2b688b1
ms.sourcegitcommit: ce154aee5b403d5c1c41da42302b896ad3cf8d82
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/07/2018
ms.locfileid: "34845818"
---
# <a name="walkthrough-create-your-first-vsto-add-in-for-powerpoint"></a>Návod: Vytvoření vaší první Add-in VSTO pro PowerPoint
  Tento návod ukazuje, jak vytvořit doplňku VSTO pro Microsoft Office PowerPoint. Funkce, které vytvoříte v tento druh řešení jsou k dispozici pro aplikace, samostatně, bez ohledu na to, které jsou otevřené prezentací. Další informace najdete v tématu [přehled vývoje řešení pro systém Office &#40;VSTO&#41;](../vsto/office-solutions-development-overview-vsto.md).  
  
 [!INCLUDE[appliesto_pptallapp](../vsto/includes/appliesto-pptallapp-md.md)]  
  
 Tento návod znázorňuje následující úlohy:  
  
-   Vytvoření projektu doplňku PowerPoint VSTO pro PowerPoint.  
  
-   Psaní kódu, který používá objektový model aplikace PowerPoint přidat textové pole pro každý nový snímek.  
  
-   Sestavení a spuštění projektu to vyzkoušíte.  
  
-   Čistí projekt tak, aby doplňku VSTO již nebude automaticky spustí na svém vývojovém počítači.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>Požadavky  
 K dokončení tohoto návodu budete potřebovat následující komponenty:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   PowerPoint  
  
## <a name="create-the-project"></a>Vytvoření projektu  
  
### <a name="to-create-a-new-project"></a>Chcete-li vytvořit nový projekt  
  
1.  Spustit [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
2.  Na **soubor** nabídky, přejděte na příkaz **nový**a potom klikněte na **projektu**.  
  
3.  Rozbalte v podokně šablon **Visual C#** nebo **jazyka Visual Basic**a potom rozbalte **Office/SharePoint**.  
  
4.  V části sada rozšířeného **Office/SharePoint** uzlu, vyberte **Office Add in** uzlu.  
  
5.  V seznamu šablon projektu vyberte projektu doplňku VSTO v PowerPointu.  
  
6.  V **název** zadejte **FirstPowerPointAddIn**.  
  
7.  Click **OK**.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] vytvoří **FirstPowerPointAddIn** projektu a otevře **ThisAddIn** souboru kódu v editoru.  
  
## <a name="write-code-that-adds-text-to-each-new-slide"></a>Napsat kód, který přidá text na každý nový snímek  
 Dál přidejte kód do souboru kódu ThisAddIn. Nový kód používá objektový model aplikace PowerPoint přidat textové pole pro každý nový snímek. Ve výchozím nastavení soubor ThisAddIn kód obsahuje následující generovaný kód:  
  
-   Částečné definice `ThisAddIn` třídy. Tato třída představuje vstupní bod pro kód a poskytuje přístup k modelu objektů aplikace PowerPoint. Další informace najdete v tématu [doplňků Program VSTO](../vsto/programming-vsto-add-ins.md). Zbývající část `ThisAddIn` třída definovaná v souboru skrytá kódu, který byste neměli upravovat.  
  
-   `ThisAddIn_Startup` a `ThisAddIn_Shutdown` obslužné rutiny událostí. Tyto obslužné rutiny událostí jsou volány při PowerPoint načte a uvolní vaší doplňku VSTO. Pomocí těchto obslužných rutin událostí k chybě při inicializaci doplňku VSTO, když je načten a vyčistit prostředky využívané třídou vaší doplňku VSTO v případě, že je odpojen. Další informace najdete v tématu [události v projektech Office](../vsto/events-in-office-projects.md).  
  
### <a name="to-add-a-text-box-to-each-new-slide"></a>Chcete-li přidat textové pole pro každý nový snímek  
  
1.  V souboru kódu ThisAddIn, přidejte následující kód, který `ThisAddIn` třídy. Tento kód definuje obslužnou rutinu události pro <xref:Microsoft.Office.Interop.PowerPoint.EApplication_Event.PresentationNewSlide> události <xref:Microsoft.Office.Interop.PowerPoint.Application> objektu.  
  
     Pokud uživatel přidá nový snímek aktivní prezentace, této obslužné rutiny události přidá textového pole na začátek nový snímek a přidá nějaký text do textového pole.  
  
     [!code-vb[Trin_PowerPointAddInTutorial#1](../vsto/codesnippet/VisualBasic/Trin_PowerPointAddInTutorial/ThisAddIn.vb#1)]
     [!code-csharp[Trin_PowerPointAddInTutorial#1](../vsto/codesnippet/CSharp/Trin_PowerPointAddInTutorial/ThisAddIn.cs#1)]  
  
2.  Pokud používáte C#, přidejte následující kód, který `ThisAddIn_Startup` obslužné rutiny události. Tento kód je vyžadován pro připojení `Application_PresentationNewSlide` obslužné rutiny události s <xref:Microsoft.Office.Interop.PowerPoint.EApplication_Event.PresentationNewSlide> událostí.  
  
     [!code-csharp[Trin_PowerPointAddInTutorial#2](../vsto/codesnippet/CSharp/Trin_PowerPointAddInTutorial/ThisAddIn.cs#2)]  
  
 Chcete-li upravit každý nový snímek, použijte předchozí příklady kódu následující objekty:  
  
-   `Application` Pole z `ThisAddIn` třídy. `Application` Pole vrátí <xref:Microsoft.Office.Interop.PowerPoint.Application> objektu, který představuje aktuální instanci aplikace PowerPoint.  
  
-   `Sld` Parametr obslužné rutiny události pro <xref:Microsoft.Office.Interop.PowerPoint.EApplication_Event.PresentationNewSlide> událostí. `Sld` Parametr <xref:Microsoft.Office.Interop.PowerPoint.Slide> objekt, který představuje nový snímek. Další informace najdete v tématu [řešení pro aplikaci PowerPoint](../vsto/powerpoint-solutions.md).  
  
## <a name="test-the-project"></a>Testování projektu  
 Při sestavení a spuštění projektu, ověřte, že textového pole se zobrazí v nových snímků, které přidáte do prezentace.  
  
### <a name="to-test-the-project"></a>Otestování projektu  
  
1.  Stiskněte klávesu **F5** sestavení a spuštění projektu.  
  
     Při sestavování projektu se zkompilovat kód do sestavení, které se umístí do výstupní složky sestavení pro projekt. Visual Studio také vytvoří sadu položky registru, které umožňují PowerPoint zjišťovat a načíst doplňku VSTO a nakonfiguruje nastavení zabezpečení na vývojovém počítači povolit doplňku VSTO ke spuštění. Další informace najdete v tématu [řešení pro systém Office sestavení](../vsto/building-office-solutions.md).  
  
2.  V aplikaci PowerPoint přidejte nový snímek do aktivní prezentace.  
  
3.  Ověřte, zda je přidána následující text do nového textového pole v horní části snímku.  
  
     **Tento text byl přidán pomocí kódu.**  
  
4.  Zavřete aplikaci PowerPoint.  
  
## <a name="clean-up-the-project"></a>Vyčistěte projekt  
 Po dokončení vývoj projektu, odeberte z vývojovém počítači doplňku VSTO sestavení, položky registru a nastavení zabezpečení. V opačném doplňku VSTO se spustí pokaždé, když na vývojovém počítači otevřete PowerPoint.  
  
### <a name="to-clean-up-your-project"></a>Vyčistěte projekt  
  
1.  V sadě Visual Studio na **sestavení** nabídky, klikněte na tlačítko **Vyčistit řešení**.  
  
## <a name="next-steps"></a>Další kroky  
 Teď, když jste vytvořili základní Add-in VSTO pro PowerPoint, další informace o tom, jak vyvíjet doplňků VSTO z těchto témat:  
  
-   Obecné programování úlohy, které můžete provádět v doplňků VSTO pro PowerPoint. Další informace najdete v tématu [doplňků Program VSTO](../vsto/programming-vsto-add-ins.md).  
  
-   Pomocí modelu objektů aplikace PowerPoint. Další informace najdete v tématu [řešení pro aplikaci PowerPoint](../vsto/powerpoint-solutions.md).  
  
-   Přizpůsobení uživatelského rozhraní PowerPoint například vytvoření vlastní karty na pásu karet nebo vytvořit vlastní vlastního podokna úloh. Další informace najdete v tématu [přizpůsobení uživatelského rozhraní Office](../vsto/office-ui-customization.md).  
  
-   Sestavování a ladění doplňků VSTO pro PowerPoint. Další informace najdete v tématu [řešení pro systém Office sestavení](../vsto/building-office-solutions.md).  
  
-   Nasazení doplňků VSTO pro PowerPoint. Další informace najdete v tématu [nasazení řešení Office](../vsto/deploying-an-office-solution.md).  
  
## <a name="see-also"></a>Viz také:  
 [Program doplňků VSTO](../vsto/programming-vsto-add-ins.md)   
 [Řešení pro aplikaci PowerPoint](../vsto/powerpoint-solutions.md)   
 [Přizpůsobení uživatelského rozhraní sady Office](../vsto/office-ui-customization.md)   
 [Sestavení řešení pro systém Office](../vsto/building-office-solutions.md)   
 [Nasazení řešení Office](../vsto/deploying-an-office-solution.md)   
 [Přehled šablon projektů Microsoft Office](../vsto/office-project-templates-overview.md)  
  
  