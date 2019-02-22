---
title: 'Postupy: Přidávání nových listů do sešitů prostřednictvím kódu programu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- workbooks, adding worksheets
- workbooks, creating worksheets
- worksheets, creating
- worksheets, adding to workbooks
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: bc23a3d0dfc18a9271db80df2cb1a42677b8ed5e
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56643688"
---
# <a name="how-to-programmatically-add-new-worksheets-to-workbooks"></a>Postupy: Přidávání nových listů do sešitů prostřednictvím kódu programu
  Můžete programově vytvořit tabulku a pak přidejte list do kolekce listů v sešitu.

 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]

## <a name="to-add-a-new-worksheet-to-a-workbook-in-a-document-level-customization"></a>Chcete-li přidat nový list do sešitu v přizpůsobení na úrovni dokumentu

1.  Použití <xref:Microsoft.Office.Interop.Excel.Worksheets.Add%2A> metodu <xref:Microsoft.Office.Interop.Excel.Sheets> kolekce.

     [!code-csharp[Trin_VstcoreExcelAutomation#15](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#15)]
     [!code-vb[Trin_VstcoreExcelAutomation#15](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#15)]

     Nový list je nativní <xref:Microsoft.Office.Interop.Excel.Worksheet> objekt a ne položka hostitele. Pokud chcete přidat <xref:Microsoft.Office.Tools.Excel.Worksheet> hostitelský objekt, měli byste přidat do listu v době návrhu.

## <a name="to-add-a-new-worksheet-to-a-workbook-in-a-vsto-add-in"></a>Chcete-li přidat nový list do sešitu v doplňku VSTO

1.  Použití <xref:Microsoft.Office.Interop.Excel.Worksheets.Add%2A> metodu <xref:Microsoft.Office.Interop.Excel.Sheets> kolekce.

     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#11](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#11)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#11](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#11)]

     Nový list je nativní <xref:Microsoft.Office.Interop.Excel.Worksheet> objekt a ne položka hostitele. Můžete vygenerovat také <xref:Microsoft.Office.Tools.Excel.Worksheet> hostitelský objekt z nativního <xref:Microsoft.Office.Interop.Excel.Worksheet> objektu. Další informace najdete v tématu [rozšíření dokumentů aplikace Word a sešitů aplikace Excel v doplňcích VSTO za běhu](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md).

## <a name="see-also"></a>Viz také:
- [Práce s listy](../vsto/working-with-worksheets.md)
- [Přehled ovládacích prvků hostitele a hostitelské položky](../vsto/host-items-and-host-controls-overview.md)
- [Postupy: Odstraňování listů ze sešitů prostřednictvím kódu programu](../vsto/how-to-programmatically-delete-worksheets-from-workbooks.md)
- [Postupy: Výběr listů prostřednictvím kódu programu](../vsto/how-to-programmatically-select-worksheets.md)
- [Automatizace aplikace Excel s použitím rozšířených objektů](../vsto/automating-excel-by-using-extended-objects.md)
- [Globální přístup k objektům v projektech pro systém Office](../vsto/global-access-to-objects-in-office-projects.md)
- [Volitelné parametry v řešeních pro systém Office](../vsto/optional-parameters-in-office-solutions.md)
