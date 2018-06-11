---
title: 'Postupy: zavírání sešitů prostřednictvím kódu programu'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- workbooks, closing
- Excel [Office development in Visual Studio], closing workbooks
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: bef95cbd79a403cf224387e754337de886a893dd
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/11/2018
ms.locfileid: "35256943"
---
# <a name="how-to-programmatically-close-workbooks"></a>Postupy: zavírání sešitů prostřednictvím kódu programu
  Můžete zavřít aktivním sešitu nebo můžete zadat sešitu zavřete.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="close-the-active-workbook"></a>Zavřete aktivním sešitu  
 Existují dva postupy pro zavření aktivním sešitu: jeden pro přizpůsobení na úrovni dokumentu a jeden pro doplňky VSTO.  
  
### <a name="to-close-the-active-workbook-in-a-document-level-customization"></a>Zavřete aktivním sešitu v přizpůsobení na úrovni dokumentu  
  
1.  Volání <xref:Microsoft.Office.Tools.Excel.Workbook.Close%2A> metoda zavřete sešit přidružené k přizpůsobení. Chcete-li použít následující příklad kódu, spusťte jej `Sheet1` – třída v projektech na úrovni dokumentu pro Excel.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#3](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#3)]
     [!code-vb[Trin_VstcoreExcelAutomation#3](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#3)]  
  
### <a name="to-close-the-active-workbook-in-a-vsto-add-in"></a>Zavřete aktivním sešitu v doplňku VSTO  
  
1.  Volání <xref:Microsoft.Office.Interop.Excel._Workbook.Close%2A> metoda zavřete aktivním sešitu. Chcete-li použít následující příklad kódu, spusťte jej `ThisAddIn` – třída v projektu doplňku VSTO pro Excel.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#1](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#1)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#1](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#1)]  
  
## <a name="close-a-workbook-that-you-specify-by-name"></a>Zavřete sešit, který určíte podle názvu  
 Způsob, jakým zavřete sešit, který zadáte název je stejný pro doplňky VSTO a úpravy na úrovni dokumentů.  
  
### <a name="to-close-a-workbook-that-you-specify-by-name"></a>Zavřete sešit, který určíte podle názvu  
  
1.  Zadejte název sešitu jako argument pro <xref:Microsoft.Office.Interop.Excel.Workbooks> kolekce. Následující příklad kódu předpokládá, že sešitu s názvem **NewWorkbook** je otevřít v aplikaci Excel.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#2](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#2)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#2](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#2)]  
  
## <a name="see-also"></a>Viz také:  
 [Práce se sešity](../vsto/working-with-workbooks.md)   
 [Postupy: ukládání sešitů prostřednictvím kódu programu](../vsto/how-to-programmatically-save-workbooks.md)   
 [Postupy: otevírání sešitů prostřednictvím kódu programu](../vsto/how-to-programmatically-open-workbooks.md)   
 [Programová omezení hostitelských položek a hostitelských ovládacích prvků](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [Volitelné parametry v řešeních pro systém Office](../vsto/optional-parameters-in-office-solutions.md)   
 [Přehled ovládacích prvků hostitele a hostitelské položky](../vsto/host-items-and-host-controls-overview.md)  
  
  