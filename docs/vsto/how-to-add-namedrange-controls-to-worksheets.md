---
title: 'Postupy: Přidání ovládacích prvků NamedRange do listů'
ms.date: 02/02/2017
ms.topic: how-to
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- ranges, adding to worksheets
- NamedRange control, adding to worksheets
- controls [Office development in Visual Studio], adding to worksheets
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 448a44c8f4bc9380a4ef1ebfec33b264e797cac8
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "85543517"
---
# <a name="how-to-add-namedrange-controls-to-worksheets"></a>Postupy: Přidání ovládacích prvků NamedRange do listů
  <xref:Microsoft.Office.Tools.Excel.NamedRange>Ovládací prvky můžete přidat do listu aplikace systém Microsoft Office Excel v době návrhu a v době běhu v projektech na úrovni dokumentu.

 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]

 Můžete také přidat <xref:Microsoft.Office.Tools.Excel.NamedRange> ovládací prvky v době běhu v projektech doplňku VSTO.

 V tomto tématu jsou popsány následující úlohy:

- [Přidat ovládací prvky NamedRange v době návrhu](#designtime)

- [Přidání ovládacích prvků NamedRange v době běhu v projektu na úrovni dokumentu](#runtimedoclevel)

- [Přidání ovládacích prvků NamedRange v době běhu v projektu doplňku VSTO](#runtimeaddin)

  Další informace o <xref:Microsoft.Office.Tools.Excel.NamedRange> ovládacích prvcích naleznete v tématu [NamedRange Control](../vsto/namedrange-control.md).

## <a name="add-namedrange-controls-at-design-time"></a><a name="designtime"></a> Přidat ovládací prvky NamedRange v době návrhu
 Existuje několik způsobů, jak přidat <xref:Microsoft.Office.Tools.Excel.NamedRange> ovládací prvky do listu v projektu na úrovni dokumentu v době návrhu: v aplikaci Excel, v sadě **nástrojů sady**Visual Studio a v okně **zdroje dat** .

 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]

### <a name="to-add-a-namedrange-control-to-a-worksheet-using-the-name-box-in-excel"></a>Přidání ovládacího prvku NamedRange do listu pomocí pole název v aplikaci Excel

1. Vyberte buňku nebo buňky, které chcete zahrnout do pojmenovaného rozsahu.

2. Do **pole název**zadejte název rozsahu a stiskněte klávesu **ENTER**.

     **Pole název** se nachází vedle řádku vzorců, přesně nad sloupce **A** listu.

### <a name="to-add-a-namedrange-control-to-a-worksheet-using-the-toolbox"></a>Přidání ovládacího prvku NamedRange na list pomocí sady nástrojů

1. Otevřete **sadu nástrojů** a klikněte na kartu **ovládací prvky aplikace Excel** .

2. Klikněte na <xref:Microsoft.Office.Tools.Excel.NamedRange> něj a přetáhněte ho na list.

     Zobrazí se dialogové okno **přidat pojmenovaný rozsah** .

3. Vyberte buňku nebo buňky, které chcete zahrnout do pojmenovaného rozsahu.

4. Klikněte na **OK**.

     Pokud nechcete, aby byl výchozí název udělen ovládacímu prvku, můžete změnit název v okně **vlastnosti** .

### <a name="to-add-a-namedrange-control-to-a-worksheet-using-the-data-sources-window"></a>Přidání ovládacího prvku NamedRange na list pomocí okna zdroje dat

1. Otevřete okno **zdroje dat** a vytvořte zdroj dat pro projekt. Další informace najdete v tématu [Přidání nových připojení](../data-tools/add-new-connections.md).

2. Přetáhněte jedno pole z okna **zdroje dat** do listu.

     <xref:Microsoft.Office.Tools.Excel.NamedRange>Do listu je přidán ovládací prvek vázaný na data. Další informace najdete v tématu [datové vazby a model Windows Forms](/dotnet/framework/winforms/data-binding-and-windows-forms).

## <a name="add-namedrange-controls-at-run-time-in-a-document-level-project"></a><a name="runtimedoclevel"></a> Přidání ovládacích prvků NamedRange v době běhu v projektu na úrovni dokumentu
 <xref:Microsoft.Office.Tools.Excel.NamedRange>V průběhu běhu můžete přidat ovládací prvek do listu programově. To umožňuje vytvořit hostitelské ovládací prvky v reakci na události. Dynamicky vytvořené pojmenované rozsahy se v listu neukládají jako hostitelské ovládací prvky při zavření listu. Další informace najdete v tématu [Přidání ovládacích prvků do dokumentů Office v době běhu](../vsto/adding-controls-to-office-documents-at-run-time.md).

### <a name="to-add-a-namedrange-control-to-a-worksheet-programmatically"></a>Postup přidání ovládacího prvku NamedRange do listu prostřednictvím kódu programu

1. V <xref:Microsoft.Office.Tools.Excel.Worksheet.Startup> obslužné rutině události třídy `Sheet1` vložte následující kód pro přidání <xref:Microsoft.Office.Tools.Excel.NamedRange> ovládacího prvku do buňky **a1** a nastavte jeho <xref:Microsoft.Office.Tools.Excel.NamedRange.Value2%2A> vlastnost na `Hello world!`

     [!code-csharp[Trin_VstcoreHostControlsExcel#3](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet1.cs#3)]
     [!code-vb[Trin_VstcoreHostControlsExcel#3](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet1.vb#3)]

## <a name="add-namedrange-controls-at-run-time-in-a-vsto-add-in-project"></a><a name="runtimeaddin"></a> Přidání ovládacích prvků NamedRange v době běhu v projektu doplňku VSTO
 Ovládací prvek můžete přidat <xref:Microsoft.Office.Tools.Excel.NamedRange> programově do libovolného otevřeného listu v projektu doplňku VSTO. Dynamicky vytvořené pojmenované rozsahy se v listu neukládají jako hostitelské ovládací prvky při zavření listu. Další informace najdete v tématu [rozšiřování dokumentů aplikace Word a sešitů aplikace Excel v doplňkech VSTO za běhu](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md).

### <a name="to-add-a-namedrange-control-to-a-worksheet-programmatically"></a>Postup přidání ovládacího prvku NamedRange do listu prostřednictvím kódu programu

1. Následující kód vygeneruje položku hostitele listu, která je založena na otevřeném listu, a poté přidá <xref:Microsoft.Office.Tools.Excel.NamedRange> ovládací prvek do buňky **a1** a nastaví jeho <xref:Microsoft.Office.Tools.Excel.NamedRange.Value2%2A> vlastnost na hodnotu `Hello world` .

     [!code-csharp[Trin_Excel_Dynamic_Controls#7](../vsto/codesnippet/CSharp/Trin_Excel_Dynamic_Controls/ThisAddIn.cs#7)]
     [!code-vb[Trin_Excel_Dynamic_Controls#7](../vsto/codesnippet/VisualBasic/Trin_Excel_Dynamic_Controls/ThisAddIn.vb#7)]

## <a name="see-also"></a>Viz také
- [Rozšiřování dokumentů aplikace Word a excelových sešitů v doplňcích VSTO za běhu](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)
- [Ovládací prvky v dokumentech Office](../vsto/controls-on-office-documents.md)
- [Ovládací prvek NamedRange](../vsto/namedrange-control.md)
- [Automatizace Excelu pomocí rozšířených objektů](../vsto/automating-excel-by-using-extended-objects.md)
- [Přehled hostitelských položek a hostitelských ovládacích prvků](../vsto/host-items-and-host-controls-overview.md)
- [Postupy: Změna velikosti ovládacích prvků NamedRange](../vsto/how-to-resize-namedrange-controls.md)
- [Programové omezení hostitelských položek a hostitelských ovládacích prvků](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)
