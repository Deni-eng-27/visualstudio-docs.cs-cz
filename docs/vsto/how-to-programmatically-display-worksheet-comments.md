---
title: "Postupy: zobrazování komentářů v listech prostřednictvím kódu programu | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- worksheets, comments
- comments, worksheets
ms.assetid: f5ce5e7f-bae4-40b7-951c-0f15b140aaf2
caps.latest.revision: "43"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 20381a6db187536dc729c08bb046152a0489e6a1
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-programmatically-display-worksheet-comments"></a>Postupy: Zobrazování komentářů v listech prostřednictvím kódu programu
  Lze programově zobrazit nebo skrýt komentářů v listech aplikace Microsoft Office Excel.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
### <a name="to-display-all-comments-on-a-worksheet-in-a-document-level-customization"></a>Chcete-li zobrazit všechny komentáře na list v přizpůsobení na úrovni dokumentu  
  
1.  Nastavte <xref:Microsoft.Office.Interop.Excel.Comment.Visible%2A> vlastnost **true** Pokud chcete zobrazit komentáře; jinak **false**. Tento kód musí být umístěny v listu třída, není v `ThisWorkbook` třídy.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#31](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#31)]
     [!code-vb[Trin_VstcoreExcelAutomation#31](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#31)]  
  
### <a name="to-display-all-comments-on-a-worksheet-in-an-application-level-vsto-add-in"></a>Chcete-li zobrazit všechny komentáře na list v doplňku VSTO úrovni aplikace  
  
1.  Nastavte <xref:Microsoft.Office.Interop.Excel.Comment.Visible%2A> vlastnost **true** Pokud chcete zobrazit komentáře; jinak **false**.  
  
     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#21](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#21)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#21](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#21)]  
  
## <a name="see-also"></a>Viz také  
 [Práce s listy](../vsto/working-with-worksheets.md)   
 [Postupy: Programové přidávání a odstraňování komentářů v listech](../vsto/how-to-programmatically-add-and-delete-worksheet-comments.md)   
 [Přehled ovládacích prvků hostitele a hostitelské položky](../vsto/host-items-and-host-controls-overview.md)  
  
  