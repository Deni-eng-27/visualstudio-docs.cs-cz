---
title: 'Postupy: Odstraňování listů ze sešitů prostřednictvím kódu programu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- workbooks, deleting worksheets
- worksheets, deleting
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 7a70e6b7c8126b2e9d2fc3274d5ecf905dce960d
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56644507"
---
# <a name="how-to-programmatically-delete-worksheets-from-workbooks"></a>Postupy: Odstraňování listů ze sešitů prostřednictvím kódu programu
  Můžete odstranit všechny listu v sešitu. Pokud chcete odstranit tabulku, pomocí hostitelská položka worksheet nebo přistupovat ke listu pomocí kolekce listů sešitu.

 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]

## <a name="use-the-worksheet-host-item"></a>Použití hostitelská položka worksheet
 Pokud v době návrhu v přizpůsobení na úrovni dokumentu byla přidána do listu, použijte <xref:Microsoft.Office.Tools.Excel.Worksheet.Delete%2A> metoda odstranění zadaného listu. Následující kód do listu odstraní ze sešitu odkazem hostitelská položka worksheet přímo.

> [!IMPORTANT]
>  Tento kód se spustí jenom v projektech, které vytvoříte pomocí některého z následujících šablon projektu:
>
> - Sešit aplikace Excel 2013
> - Šablonu v Excelu 2013
> - Sešit aplikace Excel 2010
> - Šablona aplikace Excel 2010
>
>   Pokud chcete k provedení této úlohy v jakýkoli jiný typ projektu, je nutné přidat odkaz na **Microsoft.Office.Interop.Excel** sestavení a pak pomocí třídy z tohoto sestavení k otevření sešitu a odstranění listu. Další informace najdete v tématu [jak: Cílení na aplikace Office primárních sestaveních vzájemné spolupráce](../vsto/how-to-target-office-applications-through-primary-interop-assemblies.md) a [odkaz na primární spolupracující sestavení aplikace Excel 2010](http://go.microsoft.com/fwlink/?LinkId=189585).

### <a name="to-delete-a-worksheet-by-using-a-worksheet-host-item"></a>Chcete-li odstranit na listu s použitím hostitelská položka worksheet

1.  Volání <xref:Microsoft.Office.Tools.Excel.Worksheet.Delete%2A> metoda `Sheet1`.

     [!code-csharp[Trin_VstcoreExcelAutomation#17](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#17)]
     [!code-vb[Trin_VstcoreExcelAutomation#17](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#17)]

## <a name="use-the-sheets-collection-of-the-excel-workbook"></a>Kolekce stylů Excelový sešit
 Přístup k listů prostřednictvím aplikace Microsoft Office Excel <xref:Microsoft.Office.Interop.Excel.Sheets> kolekce v následujících případech:

- Chcete odstranit tabulku v doplňku VSTO.

- List, který chcete odstranit byl vytvořen v době běhu v přizpůsobení na úrovni dokumentu.

  Následující kód odstraní tabulku ze sešitu odkazováním na listu prostřednictvím indexové číslo **seznamy** kolekce. Tento kód předpokládá, že se vytvořil programově do nového listu.

> [!IMPORTANT]
>  Pokud chcete k provedení této úlohy v jakýkoli jiný typ projektu, je nutné přidat odkaz na **Microsoft.Office.Interop.Excel** sestavení a pak pomocí třídy z tohoto sestavení k otevření sešitu a odstranění listu. Další informace najdete v tématu [jak: Cílení na aplikace Office primárních sestaveních vzájemné spolupráce](../vsto/how-to-target-office-applications-through-primary-interop-assemblies.md) a [odkaz na primární spolupracující sestavení aplikace Excel 2010](http://go.microsoft.com/fwlink/?LinkId=189585).

### <a name="to-delete-a-worksheet-by-using-the-sheets-collection-of-the-excel-workbook"></a>Chcete-li odstranit listu pomocí kolekce listech sešitu aplikace Excel

1.  Volání <xref:Microsoft.Office.Interop.Excel._Worksheet.Delete%2A> metodu <xref:Microsoft.Office.Interop.Excel.Sheets> kolekce.

     [!code-csharp[Trin_VstcoreExcelAutomation#18](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#18)]
     [!code-vb[Trin_VstcoreExcelAutomation#18](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#18)]

## <a name="see-also"></a>Viz také:
- [Práce s listy](../vsto/working-with-worksheets.md)
- [Postupy: Skrývání listů prostřednictvím kódu programu](../vsto/how-to-programmatically-hide-worksheets.md)
- [Postupy: Přesouvání listů v sešitech prostřednictvím kódu programu](../vsto/how-to-programmatically-move-worksheets-within-workbooks.md)
- [Postupy: Výběr listů prostřednictvím kódu programu](../vsto/how-to-programmatically-select-worksheets.md)
- [Postupy: Přidávání nových listů do sešitů prostřednictvím kódu programu](../vsto/how-to-programmatically-add-new-worksheets-to-workbooks.md)
- [Hostitelská položka Worksheet](../vsto/worksheet-host-item.md)
- [Globální přístup k objektům v projektech pro systém Office](../vsto/global-access-to-objects-in-office-projects.md)
- [Programová omezení hostitelských položek a hostitelských ovládacích prvků](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)
