---
title: "Postupy: mezipaměti prostřednictvím kódu programu zdroj dat v dokumentu systému Office | Microsoft Docs"
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
- Office applications [Office development in Visual Studio], data
- datasets [Office development in Visual Studio], caching
- StartCaching method
- data caching [Office development in Visual Studio], programmatically
- data [Office development in Visual Studio], caching
ms.assetid: 70b3fc06-7534-407e-898b-36f84e9a7516
caps.latest.revision: "43"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: e117243afff5cfa73cd7a27ad8ce0230d8fd512a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-programmatically-cache-a-data-source-in-an-office-document"></a>Postupy: Ukládání zdroje dat v dokumentu systému Office do mezipaměti prostřednictvím kódu programu
  Prostřednictvím kódu programu můžete přidat objekt dat do mezipaměti data v dokumentu voláním `StartCaching` metoda hostitele položky, jako například <xref:Microsoft.Office.Tools.Word.Document>, <xref:Microsoft.Office.Tools.Excel.Workbook>, nebo <xref:Microsoft.Office.Tools.Excel.Worksheet>. Odebrat datový objekt z mezipaměti dat voláním `StopCaching` metoda položky hostitele.  
  
 `StartCaching` Metoda a `StopCaching` metoda jsou obě privátní, ale jsou zobrazena v technologii IntelliSense.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
 Při použití `StartCaching` není potřeba deklarovat s metody přidat objekt dat do mezipaměti dat, datový objekt <xref:Microsoft.VisualStudio.Tools.Applications.Runtime.CachedAttribute> atribut. Datový objekt však musí splňovat určité požadavky pro přidání do datové mezipaměti. Další informace najdete v tématu [ukládání dat do mezipaměti](../vsto/caching-data.md).  
  
### <a name="to-programmatically-cache-a-data-object"></a>Na datový objekt mezipaměti prostřednictvím kódu programu  
  
1.  Datový objekt na úrovni třídy, mimo metodu deklarujte. Tento příklad předpokládá, že jsou deklarace <xref:System.Data.DataSet> s názvem `dataSet1` , kterou chcete mezipaměti prostřednictvím kódu programu.  
  
     [!code-csharp[Trin_VstcoreDataExcel#12](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet1.cs#12)]
     [!code-vb[Trin_VstcoreDataExcel#12](../vsto/codesnippet/VisualBasic/Trin_VstcoreDataExcelVB/Sheet1.vb#12)]  
  
2.  Vytvoření instance objektu data a pak zavolají `StartCaching` metodu instance dokumentu nebo listu a předejte jí názvu datový objekt.  
  
     [!code-csharp[Trin_VstcoreDataExcel#13](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet1.cs#13)]
     [!code-vb[Trin_VstcoreDataExcel#13](../vsto/codesnippet/VisualBasic/Trin_VstcoreDataExcelVB/Sheet1.vb#13)]  
  
### <a name="to-stop-caching-a-data-object"></a>Chcete-li zastavit ukládání do mezipaměti na datový objekt  
  
1.  Volání `StopCaching` metodu instance dokumentu nebo listu a předejte jí názvu datový objekt. Tento příklad předpokládá, že máte <xref:System.Data.DataSet> s názvem `dataSet1` , kterou chcete zastavit ukládání do mezipaměti.  
  
     [!code-csharp[Trin_VstcoreDataExcel#14](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet1.cs#14)]
     [!code-vb[Trin_VstcoreDataExcel#14](../vsto/codesnippet/VisualBasic/Trin_VstcoreDataExcelVB/Sheet1.vb#14)]  
  
    > [!NOTE]  
    >  Nevolejte `StopCaching` z obslužné rutiny události pro `Shutdown` událostí dokumentu nebo listu. V čase `Shutdown` událost se vyvolá, je příliš pozdě upravit datovou mezipaměť. Další informace o `Shutdown` událostí, najdete v části [události v projektech Office](../vsto/events-in-office-projects.md).  
  
## <a name="see-also"></a>Viz také  
 [Ukládání dat do mezipaměti](../vsto/caching-data.md)   
 [Postupy: ukládat Data do mezipaměti pro použití v režimu Offline nebo na serveru](../vsto/how-to-cache-data-for-use-offline-or-on-a-server.md)   
 [Postupy: mezipaměti Data v dokumentu chráněném heslem](../vsto/how-to-cache-data-in-a-password-protected-document.md)   
 [Přístup k datům v dokumentech na serveru](../vsto/accessing-data-in-documents-on-the-server.md)   
 [Ukládání dat](/visualstudio/data-tools/saving-data)  
  
  