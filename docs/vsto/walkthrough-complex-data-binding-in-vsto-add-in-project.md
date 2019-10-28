---
title: 'Návod: komplexní datová vazba v projektu doplňku VSTO'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data binding [Office development in Visual Studio], Excel
- data [Office development in Visual Studio], binding data
- complex data [Office development in Visual Studio]
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 99caf87000ea9df9260e8926eee4c7136bc9b848
ms.sourcegitcommit: dcbb876a5dd598f2538e62e1eabd4dc98595b53a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/28/2019
ms.locfileid: "72985498"
---
# <a name="walkthrough-complex-data-binding-in-vsto-add-in-project"></a>Návod: komplexní datová vazba v projektu doplňku VSTO
  Můžete navazovat data na hostitelské ovládací prvky a model Windows Forms ovládací prvky v projektech doplňku VSTO. Tento návod ukazuje, jak přidat ovládací prvky do listu aplikace systém Microsoft Office Excel a navazovat ovládací prvky na data v době běhu.

 [!INCLUDE[appliesto_xlallapp](../vsto/includes/appliesto-xlallapp-md.md)]

 Tento návod znázorňuje následující úlohy:

- Přidání ovládacího prvku <xref:Microsoft.Office.Tools.Excel.ListObject> do listu v době běhu.

- Vytvoření <xref:System.Windows.Forms.BindingSource>, které spojuje ovládací prvek s instancí datové sady.

  [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]

## <a name="prerequisites"></a>Požadavky
 K dokončení tohoto návodu budete potřebovat následující komponenty:

- [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]

- [!INCLUDE[Excel_15_short](../vsto/includes/excel-15-short-md.md)] nebo [!INCLUDE[Excel_14_short](../vsto/includes/excel-14-short-md.md)].

- Přístup ke spuštěné instanci SQL Server 2005 nebo SQL Server 2005 Express s připojenou `AdventureWorksLT` ukázkovou databází. `AdventureWorksLT`ovou databázi si můžete stáhnout z [úložiště GitHub SQL Server Samples](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks). Další informace o připojení databáze najdete v následujících tématech:

  - Postup připojení databáze pomocí SQL Server Management Studio nebo SQL Server Management Studio Express naleznete v tématu [How to: Attach a Database (SQL Server Management Studio)](/sql/relational-databases/databases/attach-a-database).

  - Postup připojení databáze pomocí příkazového řádku naleznete v tématu [How to: Attach a File Database to SQL Server Express](/previous-versions/sql/).

## <a name="create-a-new-project"></a>Vytvoření nového projektu
 Prvním krokem je vytvoření projektu doplňku VSTO pro Excel.

### <a name="to-create-a-new-project"></a>Vytvoření nového projektu

1. Vytvořte projekt doplňku VSTO pro Excel s názvem **vyplňování listů z databáze**pomocí Visual Basic nebo C#.

     Další informace najdete v tématu [Postupy: vytváření projektů pro systém Office v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md).

     Visual Studio otevře soubor `ThisAddIn.vb` nebo `ThisAddIn.cs` a přidá **listy vyplňování z databázového** projektu do **Průzkumník řešení**.

## <a name="create-a-data-source"></a>Vytvoření zdroje dat
 Pomocí okna **zdroje dat** přidejte do projektu typovou datovou sadu.

### <a name="to-add-a-typed-dataset-to-the-project"></a>Chcete-li přidat typovou datovou sadu do projektu

1. Pokud není okno **zdroje dat** viditelné, zobrazte ho tak, že v řádku nabídek vyberete možnost **Zobrazit** > **jiné** **zdroje dat** > Windows.

2. Zvolením možnosti **Přidat nový zdroj dat** spusťte **Průvodce konfigurací zdroje dat**.

3. Klikněte na **databáze**a potom klikněte na **Další**.

4. Máte-li existující připojení k databázi `AdventureWorksLT`, vyberte toto připojení a klikněte na tlačítko **Další**.

    V opačném případě klikněte na tlačítko **nové připojení**a vytvořte nové připojení pomocí dialogového okna **Přidat připojení** . Další informace najdete v tématu [Přidání nových připojení](../data-tools/add-new-connections.md).

5. Na stránce **Uložit připojovací řetězec do konfiguračního souboru aplikace** klikněte na tlačítko **Další**.

6. Na stránce **Zvolte databázové objekty** rozbalte položku **tabulky** a vyberte možnost **adresa (tabulky SalesLT)** .

7. Klikněte na tlačítko **Dokončit**.

    Do **Průzkumník řešení**se přidá soubor *AdventureWorksLTDataSet. xsd* . Tento soubor definuje následující položky:

   - Typová datová sada s názvem `AdventureWorksLTDataSet`. Tato datová sada představuje obsah tabulky **Address (tabulky SalesLT)** v databázi AdventureWorksLT.

   - TableAdapter s názvem `AddressTableAdapter`. Tento TableAdapter lze použít ke čtení a zápisu dat v `AdventureWorksLTDataSet`. Další informace najdete v tématu [TableAdapter Overview](../data-tools/fill-datasets-by-using-tableadapters.md#tableadapter-overview).

     Oba tyto objekty budete používat později v tomto návodu.

## <a name="create-controls-and-bind-controls-to-data"></a>Vytváření ovládacích prvků a vázání ovládacích prvků k datům
 Pro tento návod <xref:Microsoft.Office.Tools.Excel.ListObject> ovládací prvek zobrazí všechna data v tabulce, kterou jste vybrali, jakmile uživatel otevře sešit. Objekt list používá <xref:System.Windows.Forms.BindingSource> k připojení ovládacího prvku k databázi.

 Další informace o vázání ovládacích prvků na data najdete v tématu [vázání dat k ovládacím prvkům v řešeních pro systém Office](../vsto/binding-data-to-controls-in-office-solutions.md).

### <a name="to-add-the-list-object-dataset-and-table-adapter"></a>Přidání objektu seznamu, datové sady a adaptéru tabulky

1. V `ThisAddIn` třídy deklarujte následující ovládací prvky pro zobrazení `Address` tabulky `AdventureWorksLTDataSet` datové sady.

     [!code-csharp[Trin_ExcelAddInDatabase#1](../vsto/codesnippet/CSharp/Trin_ExcelAddInDatabase_O12/ThisAddIn.cs#1)]
     [!code-vb[Trin_ExcelAddInDatabase#1](../vsto/codesnippet/VisualBasic/Trin_ExcelAddInDatabase_O12/ThisAddIn.vb#1)]

2. V metodě `ThisAddIn_Startup` přidejte následující kód pro inicializaci datové sady a naplňte datovou sadu informacemi z datové sady `AdventureWorksLTDataSet`.

     [!code-csharp[Trin_ExcelAddInDatabase#2](../vsto/codesnippet/CSharp/Trin_ExcelAddInDatabase_O12/ThisAddIn.cs#2)]
     [!code-vb[Trin_ExcelAddInDatabase#2](../vsto/codesnippet/VisualBasic/Trin_ExcelAddInDatabase_O12/ThisAddIn.vb#2)]

3. Do metody `ThisAddIn_Startup` přidejte následující kód. Tím se vygeneruje Hostitelská položka, která rozšiřuje list. Další informace najdete v tématu [rozšiřování dokumentů aplikace Word a sešitů aplikace Excel v doplňkech VSTO za běhu](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md).

     [!code-csharp[Trin_ExcelAddInDatabase#3](../vsto/codesnippet/CSharp/Trin_ExcelAddInDatabase_O12/ThisAddIn.cs#3)]
     [!code-vb[Trin_ExcelAddInDatabase#3](../vsto/codesnippet/VisualBasic/Trin_ExcelAddInDatabase_O12/ThisAddIn.vb#3)]

4. Vytvořte rozsah a přidejte ovládací prvek <xref:Microsoft.Office.Tools.Excel.ListObject>.

     [!code-csharp[Trin_ExcelAddInDatabase#4](../vsto/codesnippet/CSharp/Trin_ExcelAddInDatabase_O12/ThisAddIn.cs#4)]
     [!code-vb[Trin_ExcelAddInDatabase#4](../vsto/codesnippet/VisualBasic/Trin_ExcelAddInDatabase_O12/ThisAddIn.vb#4)]

5. Navažte objekt seznamu na `AdventureWorksLTDataSet` pomocí <xref:System.Windows.Forms.BindingSource>. Předejte názvy sloupců, které chcete vytvořit s objektem seznamu.

     [!code-csharp[Trin_ExcelAddInDatabase#5](../vsto/codesnippet/CSharp/Trin_ExcelAddInDatabase_O12/ThisAddIn.cs#5)]
     [!code-vb[Trin_ExcelAddInDatabase#5](../vsto/codesnippet/VisualBasic/Trin_ExcelAddInDatabase_O12/ThisAddIn.vb#5)]

## <a name="test-the-add-in"></a>Test doplňku
 Když otevřete aplikaci Excel, ovládací prvek <xref:Microsoft.Office.Tools.Excel.ListObject> zobrazí data z tabulky `Address` datové sady `AdventureWorksLTDataSet`.

### <a name="to-test-the-vsto-add-in"></a>Test doplňku VSTO

- Stiskněte klávesu **F5**.

     V listu se vytvoří ovládací prvek <xref:Microsoft.Office.Tools.Excel.ListObject> s názvem `addressListObject`. Ve stejnou dobu je do projektu přidán objekt DataSet s názvem `adventureWorksLTDataSet` a <xref:System.Windows.Forms.BindingSource> s názvem `addressBindingSource`. <xref:Microsoft.Office.Tools.Excel.ListObject> je svázána s <xref:System.Windows.Forms.BindingSource>, která je zase svázána s objektem DataSet.

## <a name="see-also"></a>Viz také:

- [Data v řešeních pro systém Office](../vsto/data-in-office-solutions.md)
- [Vázání dat k ovládacím prvkům v řešeních pro systém Office](../vsto/binding-data-to-controls-in-office-solutions.md)
- [Postupy: naplnění listů daty z databáze](../vsto/how-to-populate-worksheets-with-data-from-a-database.md)
- [Postupy: Naplnění dokumentů daty z databáze](../vsto/how-to-populate-documents-with-data-from-a-database.md)
- [Postupy: Naplnění dokumentů daty ze služeb](../vsto/how-to-populate-documents-with-data-from-services.md)
- [Postupy: Naplnění dokumentů daty z objektů](../vsto/how-to-populate-documents-with-data-from-objects.md)
- [Postupy: procházení databázových záznamů na listu](../vsto/how-to-scroll-through-database-records-in-a-worksheet.md)
- [Postupy: aktualizace zdroje dat s použitím dat z hostitelského ovládacího prvku](../vsto/how-to-update-a-data-source-with-data-from-a-host-control.md)
- [Návod: jednoduché datové vazby v projektech na úrovni dokumentu](../vsto/walkthrough-simple-data-binding-in-a-document-level-project.md)
- [Návod: komplexní datové vazby v projektech na úrovni dokumentu](../vsto/walkthrough-complex-data-binding-in-a-document-level-project.md)
- [Přehled použití místních souborů databáze v řešeních pro systém Office](../vsto/using-local-database-files-in-office-solutions-overview.md)
- [Přidání nových zdrojů dat](../data-tools/add-new-data-sources.md)
- [Vytvoření vazby ovládacích prvků modelu Windows Forms k datům v sadě Visual Studio](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)
- [Přehled použití místních souborů databáze v řešeních pro systém Office](../vsto/using-local-database-files-in-office-solutions-overview.md)
- [Přehled komponenty BindingSource](/dotnet/framework/winforms/controls/bindingsource-component-overview)
