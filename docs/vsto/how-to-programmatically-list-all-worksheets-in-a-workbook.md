---
title: 'Postupy: Vytváření seznamů všech listů v sešitu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- workbooks, listing worksheets
- worksheets, listing
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 2153091b2b2abae05bf6f6c7856d2fa6d43f8967
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60109020"
---
# <a name="how-to-programmatically-list-all-worksheets-in-a-workbook"></a>Postupy: Vytváření seznamů všech listů v sešitu
  <xref:Microsoft.Office.Interop.Excel.Workbook> Poskytuje třídy <xref:Microsoft.Office.Interop.Excel.Worksheets> objektu. Tento objekt obsahuje kolekci všech <xref:Microsoft.Office.Interop.Excel.Worksheet> objektů v sešitu.

 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]

## <a name="to-list-all-existing-worksheets-in-a-workbook-in-a-document-level-customization"></a>K vypsání všech stávajících listů v sešitu v přizpůsobení na úrovni dokumentu

1. Iterovat přes <xref:Microsoft.Office.Interop.Excel.Worksheets> kolekce a odešlete název každého listu na posun buňky od <xref:Microsoft.Office.Tools.Excel.NamedRange> ovládacího prvku.

     [!code-csharp[Trin_VstcoreExcelAutomation#21](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#21)]
     [!code-vb[Trin_VstcoreExcelAutomation#21](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#21)]

## <a name="to-list-all-existing-worksheets-in-a-workbook-in-a-vsto-add-in"></a>K vypsání všech stávajících listů v sešitu v doplňku VSTO

1. Iterovat přes <xref:Microsoft.Office.Interop.Excel.Worksheets> kolekce a odešlete název každého listu na posun buňky od <xref:Microsoft.Office.Interop.Excel.Range> objektu.

     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#13](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#13)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#13](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#13)]

## <a name="see-also"></a>Viz také:
- [Práce s listy](../vsto/working-with-worksheets.md)
- [Postupy: Přidávání nových listů do sešitů prostřednictvím kódu programu](../vsto/how-to-programmatically-add-new-worksheets-to-workbooks.md)
- [Postupy: Přesouvání listů v sešitech prostřednictvím kódu programu](../vsto/how-to-programmatically-move-worksheets-within-workbooks.md)
- [Globální přístup k objektům v projektech pro systém Office](../vsto/global-access-to-objects-in-office-projects.md)
