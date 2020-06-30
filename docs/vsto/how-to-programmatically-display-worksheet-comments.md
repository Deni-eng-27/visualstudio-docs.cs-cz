---
title: 'Postupy: zobrazování komentářů v listech prostřednictvím kódu programu'
ms.date: 02/02/2017
ms.topic: how-to
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- worksheets, comments
- comments, worksheets
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 0fc84e2726cd7a70b8fc59b0f1ac2b3377f9c4af
ms.sourcegitcommit: b885f26e015d03eafe7c885040644a52bb071fae
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/30/2020
ms.locfileid: "85543361"
---
# <a name="how-to-programmatically-display-worksheet-comments"></a>Postupy: zobrazování komentářů v listech prostřednictvím kódu programu
  Komentáře můžete programově zobrazovat a skrývat v systém Microsoft Office listech aplikace Excel.

 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]

## <a name="to-display-all-comments-on-a-worksheet-in-a-document-level-customization"></a>Zobrazení všech komentářů na listu v přizpůsobení na úrovni dokumentu

1. Nastavte <xref:Microsoft.Office.Interop.Excel.Comment.Visible%2A> vlastnost na **hodnotu true** , pokud chcete zobrazit komentáře. v opačném případě **false**. Tento kód musí být umístěn ve třídě listu, nikoli ve `ThisWorkbook` třídě.

     [!code-csharp[Trin_VstcoreExcelAutomation#31](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#31)]
     [!code-vb[Trin_VstcoreExcelAutomation#31](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#31)]

## <a name="to-display-all-comments-on-a-worksheet-in-an-application-level-vsto-add-in"></a>Zobrazení všech komentářů na listu v doplňku VSTO na úrovni aplikace

1. Nastavte <xref:Microsoft.Office.Interop.Excel.Comment.Visible%2A> vlastnost na **hodnotu true** , pokud chcete zobrazit komentáře. v opačném případě **false**.

     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#21](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#21)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#21](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#21)]

## <a name="see-also"></a>Viz také
- [Práce s listy](../vsto/working-with-worksheets.md)
- [Postupy: přidávání a odstraňování komentářů v listech prostřednictvím kódu programu](../vsto/how-to-programmatically-add-and-delete-worksheet-comments.md)
- [Přehled hostitelských položek a hostitelských ovládacích prvků](../vsto/host-items-and-host-controls-overview.md)
