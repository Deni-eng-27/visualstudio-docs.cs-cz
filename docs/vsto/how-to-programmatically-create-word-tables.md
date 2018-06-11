---
title: 'Postupy: vytváření tabulek aplikace Word prostřednictvím kódu programu'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- documents [Office development in Visual Studio], adding tables
- tables [Office development in Visual Studio], adding to documents
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: a44c87a796a5f4d9add4dad122933fbbbd2fe13c
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/11/2018
ms.locfileid: "35257836"
---
# <a name="how-to-programmatically-create-word-tables"></a>Postupy: vytváření tabulek aplikace Word prostřednictvím kódu programu
  <xref:Microsoft.Office.Interop.Word.Tables> Kolekce je členem skupiny <xref:Microsoft.Office.Interop.Word.Document>, <xref:Microsoft.Office.Tools.Word.Document>, <xref:Microsoft.Office.Interop.Word.Selection>, a <xref:Microsoft.Office.Interop.Word.Range> třídy, které znamená, že můžete vytvořit tabulku v některém z těchto kontexty. Můžete použít <xref:Microsoft.Office.Interop.Word.Tables.Add%2A> metodu <xref:Microsoft.Office.Interop.Word.Tables> kolekci v zadaném rozsahu přidat tabulku.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
## <a name="create-tables-in-document-level-customizations"></a>Vytváření tabulek v přizpůsobeních na úrovni dokumentu  
  
### <a name="to-add-a-simple-table-to-a-document"></a>Chcete-li přidat jednoduché tabulky do dokumentu.  
  
-   Použití <xref:Microsoft.Office.Interop.Word.Tables.Add%2A> metody přidat tabulku tři řádky a čtyři sloupce na začátku dokumentu.  
  
     Chcete-li použít následující příklad kódu, spusťte jej z `ThisDocument` třídy ve vašem projektu.  
  
     [!code-vb[Trin_VstcoreWordAutomation#86](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#86)]
     [!code-csharp[Trin_VstcoreWordAutomation#86](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#86)]  
  
 Když vytvoříte tabulku, se automaticky přidá do <xref:Microsoft.Office.Interop.Word.Tables> kolekce <xref:Microsoft.Office.Tools.Word.Document> hostitelská položka. Pak najdete v tabulce podle čísla položky pomocí <xref:Microsoft.Office.Interop.Word.Tables.Item%2A> vlastnost, jak je znázorněno v následujícím kódu.  
  
### <a name="to-refer-to-a-table-by-item-number"></a>Pro odkaz na tabulku číslem položky  
  
1.  Použití <xref:Microsoft.Office.Interop.Word.Tables.Item%2A> vlastností a zadejte číslo tabulky, která chcete odkazovat.  
  
     Chcete-li použít následující příklad kódu, spusťte jej z `ThisDocument` třídy ve vašem projektu.  
  
     [!code-vb[Trin_VstcoreWordAutomation#87](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#87)]
     [!code-csharp[Trin_VstcoreWordAutomation#87](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#87)]  
  
 Každý <xref:Microsoft.Office.Interop.Word.Table> objekt má také <xref:Microsoft.Office.Interop.Word.Table.Range%2A> vlastnost, která umožňuje nastavit formátování atributy.  
  
### <a name="to-apply-a-style-to-a-table"></a>Pokud chcete použít styl do tabulky  
  
1.  Použití <xref:Microsoft.Office.Interop.Word.Table.Style%2A> vlastnost použít jeden z předdefinovaných stylů aplikace Word na tabulku.  
  
     Chcete-li použít následující příklad kódu, spusťte jej z `ThisDocument` třídy ve vašem projektu.  
  
     [!code-vb[Trin_VstcoreWordAutomation#88](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#88)]
     [!code-csharp[Trin_VstcoreWordAutomation#88](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#88)]  
  
## <a name="create-tables-in-vsto-add-ins"></a>Vytváření tabulek v doplňků VSTO  
  
### <a name="to-add-a-simple-table-to-a-document"></a>Chcete-li přidat jednoduché tabulky do dokumentu.  
  
-   Použití <xref:Microsoft.Office.Interop.Word.Tables.Add%2A> metody přidat tabulku tři řádky a čtyři sloupce na začátku dokumentu.  
  
     Následující příklad kódu přidá tabulku pro aktivní dokument. Pokud chcete použít v tomto příkladu, spusťte z `ThisAddIn` třídy ve vašem projektu.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#86](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#86)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#86](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#86)]  
  
 Když vytvoříte tabulku, se automaticky přidá do <xref:Microsoft.Office.Interop.Word.Tables> kolekce <xref:Microsoft.Office.Interop.Word.Document>. Pak najdete v tabulce podle čísla položky pomocí <xref:Microsoft.Office.Interop.Word.Tables.Item%2A> vlastnost, jak je znázorněno v následujícím kódu.  
  
### <a name="to-refer-to-a-table-by-item-number"></a>Pro odkaz na tabulku číslem položky  
  
1.  Použití <xref:Microsoft.Office.Interop.Word.Tables.Item%2A> vlastností a zadejte číslo tabulky, která chcete odkazovat.  
  
     Následující příklad kódu používá aktivní dokument. Pokud chcete použít v tomto příkladu, spusťte z `ThisAddIn` třídy ve vašem projektu.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#87](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#87)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#87](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#87)]  
  
 Každý <xref:Microsoft.Office.Interop.Word.Table> objekt má také <xref:Microsoft.Office.Interop.Word.Table.Range%2A> vlastnost, která umožňuje nastavit formátování atributy.  
  
### <a name="to-apply-a-style-to-a-table"></a>Pokud chcete použít styl do tabulky  
  
1.  Použití <xref:Microsoft.Office.Interop.Word.Table.Style%2A> vlastnost použít jeden z předdefinovaných stylů aplikace Word na tabulku.  
  
     Následující příklad kódu používá aktivní dokument. Pokud chcete použít v tomto příkladu, spusťte z `ThisAddIn` třídy ve vašem projektu.  
  
     [!code-vb[Trin_VstcoreWordAutomationAddIn#88](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationAddIn/ThisAddIn.vb#88)]
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#88](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationAddIn/ThisAddIn.cs#88)]  
  
## <a name="see-also"></a>Viz také:  
 [Postupy: přidávání textu a formátování do buněk tabulek aplikace Word prostřednictvím kódu programu](../vsto/how-to-programmatically-add-text-and-formatting-to-cells-in-word-tables.md)   
 [Postupy: Programové přidávání řádků a sloupců do tabulek aplikace Word](../vsto/how-to-programmatically-add-rows-and-columns-to-word-tables.md)   
 [Postupy: naplnění prostřednictvím kódu programu tabulek aplikace Word prostřednictvím vlastnosti dokumentu](../vsto/how-to-programmatically-populate-word-tables-with-document-properties.md)   
 [Volitelné parametry v řešeních pro systém Office](../vsto/optional-parameters-in-office-solutions.md)  
  
  