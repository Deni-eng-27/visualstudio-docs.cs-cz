---
title: 'Postupy: Tisk dokumentů prostřednictvím kódu programu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Word [Office development in Visual Studio], printing documents
- documents [Office development in Visual Studio], printing
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 252891f603f974b43fa9a609bd9bbde9dde2f7f3
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56654071"
---
# <a name="how-to-programmatically-print-documents"></a>Postupy: Tisk dokumentů prostřednictvím kódu programu
  Můžete vytisknout celý dokument aplikace Microsoft Office Word nebo část dokumentu, se výchozí tiskárna.

 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]

## <a name="print-a-document-that-is-part-of-a-document-level-customization"></a>Vytisknout dokument, který je součástí přizpůsobení na úrovni dokumentu

### <a name="to-print-the-entire-document"></a>Chcete-li vytisknout celý dokument

1.  Volání <xref:Microsoft.Office.Tools.Word.Document.PrintOut%2A> metodu `ThisDocument` třídu ve vašem projektu, chcete-li vytisknout celý dokument. Pokud chcete použít tento příklad, spusťte kód z `ThisDocument` třídy.

     [!code-vb[Trin_VstcoreWordAutomation#11](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#11)]
     [!code-csharp[Trin_VstcoreWordAutomation#11](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#11)]

### <a name="to-print-the-current-page-of-the-document"></a>Tisk aktuální stránky dokumentu

1.  Volání <xref:Microsoft.Office.Tools.Word.Document.PrintOut%2A> metodu `ThisDocument` třídy ve vašem projektu a určit, že jedna kopie aktuální stránky vytištěn. Pokud chcete použít tento příklad, spusťte kód z `ThisDocument` třídy.

     [!code-vb[Trin_VstcoreWordAutomation#12](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#12)]
     [!code-csharp[Trin_VstcoreWordAutomation#12](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#12)]

## <a name="print-a-document-by-using-a-vsto-add-in"></a>Tisk dokumentu pomocí doplňku VSTO

### <a name="to-print-an-entire-document"></a>Chcete-li vytisknout celý dokument

1.  Volání <xref:Microsoft.Office.Interop.Word._Document.PrintOut%2A> metodu <xref:Microsoft.Office.Interop.Word.Document> objekt, který chcete vytisknout. Následující příklad kódu zobrazí aktivní dokument. Pokud chcete použít tento příklad, spusťte kód z `ThisAddIn` třídu ve vašem projektu.

     [!code-vb[Trin_VstcoreWordAutomationAddIn#11](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#11)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#11](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#11)]

### <a name="to-print-the-current-page-of-a-document"></a>Tisk aktuální stránky dokumentu

1.  Volání <xref:Microsoft.Office.Interop.Word._Document.PrintOut%2A> metodu <xref:Microsoft.Office.Interop.Word.Document> objekt, který chcete vytisknout a určit, že jedna kopie aktuální stránky vytištěn. Následující příklad kódu zobrazí aktivní dokument. Pokud chcete použít tento příklad, spusťte kód z `ThisAddIn` třídu ve vašem projektu.

     [!code-vb[Trin_VstcoreWordAutomationAddIn#12](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#12)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#12](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#12)]

## <a name="see-also"></a>Viz také:
- [Volitelné parametry v řešeních pro systém Office](../vsto/optional-parameters-in-office-solutions.md)
