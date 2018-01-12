---
title: "Postupy: otevírání dokumentů aplikace Visio prostřednictvím kódu programu | Microsoft Docs"
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
- documents [Office development in Visual Studio], opening Visio documents
- Visio [Office development in Visual Studio], opening Visio documents
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: a558e0cd069c91a490f039198b59aa3a89c83662
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-programmatically-open-visio-documents"></a>Postupy: Otevírání dokumentů aplikace Visio prostřednictvím kódu programu
  Existují dvě metody pro otevírání stávajících dokumentů Microsoft Office Visio: otevřete a OpenEx. Metoda OpenEx je stejná jako metodu otevřené, s tím rozdílem, že poskytuje argumenty, ve kterých můžete zadat volající, jak dokument se otevře.  
  
 Podrobnosti o objektu modelu najdete v tématu referenční dokumentaci VBA pro [Microsoft.Office.Interop.Visio.Documents.Open](https://msdn.microsoft.com/library/office/ff765240.aspx) metoda a [Microsoft.Office.Interop.Visio.Documents.OpenEx](https://msdn.microsoft.com/library/office/ff767229.aspx) Metoda.  
  
## <a name="opening-a-visio-document"></a>Otevírání dokumentů aplikace Visio  
  
#### <a name="to-open-a-visio-document"></a>Otevření dokumentů aplikace Visio  
  
-   Volání metody Microsoft.Office.Interop.Visio.Documents.Open a zadejte plně kvalifikovanou cestu dokumentů aplikace Visio.  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#5](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#5)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#5](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#5)]  
  
## <a name="opening-a-visio-document-with-specified-arguments"></a>Otevírání dokumentů aplikace Visio se zadanými argumenty  
  
#### <a name="to-open-a-visio-document-as-read-only-and-docked"></a>Otevření dokumentů aplikace Visio jako jen pro čtení a ukotveného  
  
-   Volání metody Microsoft.Office.Interop.Visio.Documents.OpenEx, zadejte plně kvalifikovanou cestu dokumentů aplikace Visio a zahrnují argumenty, které chcete použít – v tomto případu, ukotveného a jen pro čtení.  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#6](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#6)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#6](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#6)]  
  
## <a name="compiling-the-code"></a>Probíhá kompilace kódu  
 Tento příklad kódu vyžaduje následující:  
  
-   Dokumentů aplikace Visio s názvem `myDrawing.vsd` musí být umístěn v adresáři s názvem `Test` ve složce Dokumenty (pro Windows XP a starší) nebo ve složce Dokumenty (pro systém Windows Vista).  
  
## <a name="see-also"></a>Viz také  
 [Řešení pro aplikaci Visio](../vsto/visio-solutions.md)   
 [Přehled modelu objektů aplikace Visio](../vsto/visio-object-model-overview.md)   
 [Postupy: vytváření nových dokumentů aplikace Visio prostřednictvím kódu programu](../vsto/how-to-programmatically-create-new-visio-documents.md)   
 [Postupy: zavírání dokumentů aplikace Visio prostřednictvím kódu programu](../vsto/how-to-programmatically-close-visio-documents.md)   
 [Postupy: ukládání dokumentů aplikace Visio prostřednictvím kódu programu](../vsto/how-to-programmatically-save-visio-documents.md)   
 [Postupy: Tisk dokumentů aplikace Visio prostřednictvím kódu programu](../vsto/how-to-programmatically-print-visio-documents.md)  
  
  