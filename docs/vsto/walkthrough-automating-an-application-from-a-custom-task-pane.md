---
title: 'Návod: Automatizace aplikace z vlastního podokna úloh'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- task panes [Office development in Visual Studio], PowerPoint
- PowerPoint [Office development in Visual Studio], custom task panes
- automating Office applications
- custom task panes [Office development in Visual Studio], automating applications
- custom task panes [Office development in Visual Studio], PowerPoint
- task panes [Office development in Visual Studio], automating applications
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: f5135e96125192d7ed125287aa47c839031824fe
ms.sourcegitcommit: 2da366ba9ad124366f6502927ecc720985fc2f9e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68871945"
---
# <a name="walkthrough-automate-an-application-from-a-custom-task-pane"></a>Návod: Automatizace aplikace z vlastního podokna úloh
  Tento návod ukazuje, jak vytvořit vlastní podokno úloh, které automatizuje PowerPoint. Vlastní podokno úloh vloží data do snímku, když uživatel klikne <xref:System.Windows.Forms.MonthCalendar> na ovládací prvek, který se nachází v podokně vlastní úlohy.

 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]

 I když tento návod používá specifickou aplikaci PowerPoint, koncepce znázorněné v tomto návodu se vztahují na všechny aplikace, které jsou uvedeny výše.

 Tento návod znázorňuje následující úlohy:

- Návrh uživatelského rozhraní vlastního podokna úloh.

- Automatizace PowerPointu z vlastního podokna úloh.

- Zobrazení vlastního podokna úloh v aplikaci PowerPoint.

> [!NOTE]
> Váš počítač může v následujících pokynech zobrazovat odlišné názvy nebo umístění některých prvků uživatelského rozhraní sady Visual Studio. Tyto prvky jsou určeny edicí sady Visual Studio a použitým nastavením. Další informace najdete v tématu [Přizpůsobení integrovaného vývojového prostředí (IDE) sady Visual Studio](../ide/personalizing-the-visual-studio-ide.md).

## <a name="prerequisites"></a>Požadavky
 K dokončení tohoto návodu budete potřebovat následující komponenty:

- [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]

- Microsoft PowerPoint 2010 nebo [!INCLUDE[PowerPoint_15_short](../vsto/includes/powerpoint-15-short-md.md)].

## <a name="create-the-add-in-project"></a>Vytvoření projektu doplňku
 Prvním krokem je vytvoření projektu doplňku VSTO pro PowerPoint.

### <a name="to-create-a-new-project"></a>Vytvoření nového projektu

1. Pomocí šablony projektu doplňku aplikace PowerPoint vytvořte projekt doplňku VSTO pro PowerPoint s názvem **MyAddIn**. Další informace najdete v tématu [jak: Vytváření projektů Office v sadě Visual](../vsto/how-to-create-office-projects-in-visual-studio.md)Studio.

     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]otevře soubor kódu **ThisAddIn.cs** nebo **ThisAddIn. vb** a přidá projekt **MyAddIn** do **Průzkumník řešení**.

## <a name="design-the-user-interface-of-the-custom-task-pane"></a>Návrh uživatelského rozhraní vlastního podokna úloh
 Neexistuje žádný vizuální Návrhář pro vlastní podokna úloh, ale můžete navrhnout uživatelský ovládací prvek s požadovaným rozložením. Později v tomto návodu přidáte uživatelský ovládací prvek do vlastního podokna úloh.

#### <a name="to-design-the-user-interface-of-the-custom-task-pane"></a>Návrh uživatelského rozhraní vlastního podokna úloh

1. V nabídce **projekt** klikněte na příkaz **Přidat uživatelský ovládací prvek**.

2. V dialogovém okně **Přidat novou položku** změňte název uživatelského ovládacího prvku na **MyUserControl**a klikněte na tlačítko **Přidat**.

     Uživatelský ovládací prvek se otevře v návrháři.

3. Na kartě **běžné ovládací prvky** **panelu nástrojů**přetáhněte ovládací prvek **MonthCalendar** do uživatelského ovládacího prvku.

     Pokud je ovládací prvek **MonthCalendar** větší než návrhová plocha uživatelského ovládacího prvku, změňte velikost uživatelského ovládacího prvku tak, aby odpovídala ovládacímu prvku **MonthCalendar** .

## <a name="automate-powerpoint-from-the-custom-task-pane"></a>Automatizace PowerPointu z vlastního podokna úloh
 Účelem doplňku VSTO je umístit vybrané datum na první snímek aktivní prezentace. <xref:System.Windows.Forms.MonthCalendar.DateChanged> Použijte událost ovládacího prvku k přidání vybraného data vždy, když se změní.

### <a name="to-automate-powerpoint-from-the-custom-task-pane"></a>Automatizace PowerPointu z vlastního podokna úloh

1. V Návrháři dvakrát klikněte <xref:System.Windows.Forms.MonthCalendar> na ovládací prvek.

     Otevře se soubor **MyUserControl.cs** nebo **MyUserControl. vb** a vytvoří se <xref:System.Windows.Forms.MonthCalendar.DateChanged> obslužná rutina události pro událost.

2. Do horní části souboru přidejte následující kód. Tento kód vytvoří aliasy pro <xref:Microsoft.Office.Core> obory názvů [aplikace a PowerPoint](/previous-versions/office/developer/office-2010/ff763170%28v%3doffice.14%29) .

     [!code-csharp[Trin_TaskPaneMonthCalendar#1](../vsto/codesnippet/CSharp/Trin_TaskPaneMonthCalendar/MyUserControl.cs#1)]
     [!code-vb[Trin_TaskPaneMonthCalendar#1](../vsto/codesnippet/VisualBasic/Trin_TaskPaneMonthCalendar/MyUserControl.vb#1)]

3. Do `MyUserControl` třídy přidejte následující kód. Tento kód deklaruje objekt [Shape](/previous-versions/office/developer/office-2010/ff760244(v=office.14)) jako člena `MyUserControl`. V následujícím kroku použijete tento [obrazec](/previous-versions/office/developer/office-2010/ff760244(v=office.14)) k přidání textového pole do snímku v aktivní prezentaci.

     [!code-csharp[Trin_TaskPaneMonthCalendar#2](../vsto/codesnippet/CSharp/Trin_TaskPaneMonthCalendar/MyUserControl.cs#2)]
     [!code-vb[Trin_TaskPaneMonthCalendar#2](../vsto/codesnippet/VisualBasic/Trin_TaskPaneMonthCalendar/MyUserControl.vb#2)]

4. Proměnnou obslužné rutiny události nahraďte následujícím kódem. `monthCalendar1_DateChanged` Tento kód přidá do prvního snímku v aktivní prezentaci textové pole a pak do textového pole přidá aktuálně vybrané datum. Tento kód používá `Globals.ThisAddIn` objekt pro přístup k objektovému modelu aplikace PowerPoint.

     [!code-csharp[Trin_TaskPaneMonthCalendar#3](../vsto/codesnippet/CSharp/Trin_TaskPaneMonthCalendar/MyUserControl.cs#3)]
     [!code-vb[Trin_TaskPaneMonthCalendar#3](../vsto/codesnippet/VisualBasic/Trin_TaskPaneMonthCalendar/MyUserControl.vb#3)]

5. V **Průzkumník řešení**klikněte pravým tlačítkem na projekt **MyAddIn** a pak klikněte na **sestavit**. Ověřte, že se projekt vytváří bez chyb.

## <a name="display-the-custom-task-pane"></a>Zobrazit vlastní podokno úloh
 Pokud chcete zobrazit vlastní podokno úloh při spuštění doplňku VSTO, přidejte uživatelský ovládací prvek do podokna úloh v <xref:Microsoft.Office.Tools.AddIn.Startup> obslužné rutině události doplňku VSTO.

### <a name="to-display-the-custom-task-pane"></a>Zobrazení vlastního podokna úloh

1. V **Průzkumník řešení**rozbalte možnost **PowerPoint**.

2. Klikněte pravým tlačítkem na **ThisAddIn.cs** nebo **ThisAddIn. vb** a klikněte na **Zobrazit kód**.

3. Do `ThisAddIn` třídy přidejte následující kód. Tento kód deklaruje instance `MyUserControl` a <xref:Microsoft.Office.Tools.CustomTaskPane> jako členy `ThisAddIn` třídy.

     [!code-vb[Trin_TaskPaneMonthCalendar#4](../vsto/codesnippet/VisualBasic/Trin_TaskPaneMonthCalendar/ThisAddIn.vb#4)]
     [!code-csharp[Trin_TaskPaneMonthCalendar#4](../vsto/codesnippet/CSharp/Trin_TaskPaneMonthCalendar/ThisAddIn.cs#4)]

4. Proměnnou obslužné rutiny události nahraďte následujícím kódem. `ThisAddIn_Startup` Tento kód vytvoří nový <xref:Microsoft.Office.Tools.CustomTaskPane> `MyUserControl` přidáním objektu do `CustomTaskPanes` kolekce. Kód také zobrazí podokno úloh.

     [!code-vb[Trin_TaskPaneMonthCalendar#5](../vsto/codesnippet/VisualBasic/Trin_TaskPaneMonthCalendar/ThisAddIn.vb#5)]
     [!code-csharp[Trin_TaskPaneMonthCalendar#5](../vsto/codesnippet/CSharp/Trin_TaskPaneMonthCalendar/ThisAddIn.cs#5)]

## <a name="test-the-add-in"></a>Test doplňku
 Při spuštění projektu se otevře PowerPoint a v doplňku VSTO se zobrazí vlastní podokno úloh. Klikněte na <xref:System.Windows.Forms.MonthCalendar> ovládací prvek pro otestování kódu.

### <a name="to-test-your-vsto-add-in"></a>Testování doplňku VSTO

1. Stisknutím klávesy **F5** spusťte projekt.

2. Potvrďte, že se vlastní podokno úloh zobrazuje.

3. Klikněte na datum v <xref:System.Windows.Forms.MonthCalendar> ovládacím prvku v podokně úloh.

     Datum je vloženo do prvního snímku v aktivní prezentaci.

## <a name="next-steps"></a>Další postup
 Další informace o tom, jak vytvořit vlastní podokna úloh, najdete v těchto tématech:

- Vytvoření vlastního podokna úloh v doplňku VSTO pro jinou aplikaci. Další informace o aplikacích, které podporují vlastní podokna úloh, najdete v tématu [vlastní podokna úloh](../vsto/custom-task-panes.md).

- Umožňuje vytvořit tlačítko pásu karet, které se dá použít k skrytí nebo zobrazení vlastního podokna úloh. Další informace najdete v tématu [Návod: Synchronizace vlastního podokna úloh s tlačítkem](../vsto/walkthrough-synchronizing-a-custom-task-pane-with-a-ribbon-button.md)na pásu karet

- Slouží k vytvoření vlastního podokna úloh pro každou e-mailovou zprávu, která je otevřena v aplikaci Outlook. Další informace najdete v tématu [Návod: Zobrazení vlastních podoken úloh s e-mailovými](../vsto/walkthrough-displaying-custom-task-panes-with-e-mail-messages-in-outlook.md)zprávami v Outlooku

## <a name="see-also"></a>Viz také:
- [Vlastní podokna úloh](../vsto/custom-task-panes.md)
- [Postupy: Přidání vlastního podokna úloh do aplikace](../vsto/how-to-add-a-custom-task-pane-to-an-application.md)
- [Návod: Synchronizace vlastního podokna úloh s tlačítkem na pásu karet](../vsto/walkthrough-synchronizing-a-custom-task-pane-with-a-ribbon-button.md)
- [Návod: Zobrazení vlastních podoken úloh s e-mailovými zprávami v Outlooku](../vsto/walkthrough-displaying-custom-task-panes-with-e-mail-messages-in-outlook.md)
