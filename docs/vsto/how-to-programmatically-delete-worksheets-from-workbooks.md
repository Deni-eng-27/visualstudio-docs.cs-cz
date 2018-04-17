---
title: 'Postupy: odstraňování listů ze sešitů prostřednictvím kódu programu | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- workbooks, deleting worksheets
- worksheets, deleting
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 4d6e9095890212debb8ab845ac7411c734b9a427
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-programmatically-delete-worksheets-from-workbooks"></a>Postupy: Odstraňování listů ze sešitů prostřednictvím kódu programu
  Můžete odstranit všechny listu sešitu. Pokud chcete odstranit listu, použijte hostitelská položka worksheet nebo přístup listu pomocí kolekce listy sešitu.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="using-the-worksheet-host-item"></a>Pomocí hostitelská položka Worksheet  
 Pokud list byl přidán v době návrhu přizpůsobení na úrovni dokumentu, použijte <xref:Microsoft.Office.Tools.Excel.Worksheet.Delete%2A> metodu za účelem odstranění zadaného listu. Následující kód do listu odstraní ze sešitu odkazem hostitelská položka worksheet přímo.  
  
> [!IMPORTANT]  
>  Tento kód spustí jenom v projektech, které vytvoříte pomocí některé z následujících šablon projektu:  
>   
>  -   Sešit aplikace Excel 2013  
> -   Šablona Excelu 2013  
> -   Sešit aplikace Excel 2010  
> -   Šablona aplikace Excel 2010  
>   
>  Pokud chcete k provedení této úlohy v jiný typ projektu, musíte přidat odkaz na **Microsoft.Office.Interop.Excel** sestavení a pak musí otevřít sešit, a odstraňovat list pomocí třídy z tohoto sestavení. Další informace najdete v tématu [postup: cíl aplikací prostřednictvím primární zprostředkovatel komunikace s objekty sestavení sady Office](../vsto/how-to-target-office-applications-through-primary-interop-assemblies.md) a [odkaz na sestavení zprostředkovatel komunikace s objekty aplikace Excel 2010 primární](http://go.microsoft.com/fwlink/?LinkId=189585).  
  
#### <a name="to-delete-a-worksheet-by-using-a-worksheet-host-item"></a>Chcete-li odstranit na listu s použitím hostitelská položka worksheet  
  
1.  Volání <xref:Microsoft.Office.Tools.Excel.Worksheet.Delete%2A> metodu `Sheet1`.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#17](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#17)]
     [!code-vb[Trin_VstcoreExcelAutomation#17](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#17)]  
  
## <a name="using-the-sheets-collection-of-the-excel-workbook"></a>Pomocí kolekce listy sešitu aplikace Excel  
 Přístup k listů prostřednictvím aplikace Microsoft Office Excel <xref:Microsoft.Office.Interop.Excel.Sheets> kolekce v následujících případech:  
  
-   Chcete odstranit pracovní list v doplňku VSTO.  
  
-   Sešit, který chcete odstranit byl vytvořen v době běhu v přizpůsobení na úrovni dokumentu.  
  
 Následující kód odstraní list ze sešitu odkazem na list prostřednictvím indexové číslo **listy** kolekce. Tento kód předpokládá, že do nového sešitu vytvořil prostřednictvím kódu programu.  
  
> [!IMPORTANT]  
>  Pokud chcete k provedení této úlohy v jiný typ projektu, musíte přidat odkaz na **Microsoft.Office.Interop.Excel** sestavení a pak musí otevřít sešit, a odstraňovat list pomocí třídy z tohoto sestavení. Další informace najdete v tématu [postup: cíl aplikací prostřednictvím primární zprostředkovatel komunikace s objekty sestavení sady Office](../vsto/how-to-target-office-applications-through-primary-interop-assemblies.md) a [odkaz na sestavení zprostředkovatel komunikace s objekty aplikace Excel 2010 primární](http://go.microsoft.com/fwlink/?LinkId=189585).  
  
#### <a name="to-delete-a-worksheet-by-using-the-sheets-collection-of-the-excel-workbook"></a>Chcete-li odstranit list pomocí kolekce listy sešitu aplikace Excel  
  
1.  Volání <xref:Microsoft.Office.Interop.Excel._Worksheet.Delete%2A> metodu <xref:Microsoft.Office.Interop.Excel.Sheets> kolekce.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#18](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#18)]
     [!code-vb[Trin_VstcoreExcelAutomation#18](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#18)]  
  
## <a name="see-also"></a>Viz také  
 [Práce s listy](../vsto/working-with-worksheets.md)   
 [Postupy: skrývání listů prostřednictvím kódu programu](../vsto/how-to-programmatically-hide-worksheets.md)   
 [Postupy: přesouvání listů v sešitech prostřednictvím kódu programu](../vsto/how-to-programmatically-move-worksheets-within-workbooks.md)   
 [Postupy: výběr listů prostřednictvím kódu programu](../vsto/how-to-programmatically-select-worksheets.md)   
 [Postupy: přidávání nových listů do sešitů prostřednictvím kódu programu](../vsto/how-to-programmatically-add-new-worksheets-to-workbooks.md)   
 [Hostitelská položka Worksheet](../vsto/worksheet-host-item.md)   
 [Globální přístup k objektům v projektech pro systém Office](../vsto/global-access-to-objects-in-office-projects.md)   
 [Programová omezení hostitelských položek a hostitelských ovládacích prvků](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)  
  
  