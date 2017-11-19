---
title: "Postupy: čtení z a zapisovat do vlastností dokumentu | Microsoft Docs"
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
- Word [Office development in Visual Studio], document properties
- documents [Office development in Visual Studio], properties
- document properties [Office development in Visual Studio]
- Excel [Office development in Visual Studio], document properties
ms.assetid: e9ef9fa3-36b9-48fb-8148-f5152463c03c
caps.latest.revision: "54"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: ca687f9482d65621ad848c2ca6459c6fe782f8ba
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-read-from-and-write-to-document-properties"></a>Postupy: Čtení z vlastností dokumentu a zápis do nich
  Vlastnosti dokumentu společně s dokumentem můžete uložit. Aplikace Office zadat počet předdefinované vlastnosti, například autora, název a předmět. Toto téma ukazuje, jak nastavit vlastnosti dokumentu v aplikaci Microsoft Office Excel a Microsoft Office Word.  
  
 ![odkaz na video](../vsto/media/playvideo.gif "odkaz na video") související Videoukázka, najdete v části [jak provést I: přístup a upravit vlastnosti vlastní dokumentu v Microsoft Wordu?](http://go.microsoft.com/fwlink/?LinkId=136772).  
  
 [!INCLUDE[appliesto_docprops](../vsto/includes/appliesto-docprops-md.md)]  
  
## <a name="setting-document-properties-in-excel"></a>Nastavení vlastností dokumentu v aplikaci Excel  
 Chcete-li pracovat s předdefinované vlastnosti v aplikaci Excel, použijte následující vlastnosti:  
  
-   V projektech na úrovni dokumentu, použijte <xref:Microsoft.Office.Tools.Excel.Workbook.BuiltinDocumentProperties%2A> vlastnost `ThisWorkbook` třídy.  
  
-   V projektu doplňku VSTO, pomocí <xref:Microsoft.Office.Interop.Excel._Workbook.BuiltinDocumentProperties%2A> vlastnost <xref:Microsoft.Office.Interop.Excel.Workbook> objektu.  
  
 Tyto vlastnosti vrátit <xref:Microsoft.Office.Core.DocumentProperties> objekt, který je kolekce z <xref:Microsoft.Office.Core.DocumentProperty> objekty. Můžete použít `Item` vlastnosti kolekce pro načtení určité vlastnosti, pomocí názvu nebo podle indexu v kolekci.  
  
 Následující příklad kódu ukazuje, jak změnit integrované **číslo revize** vlastnosti v projektech na úrovni dokumentu.  
  
#### <a name="to-change-the-revision-number-property-in-excel"></a>Chcete-li změnit vlastnost číslo revize v aplikaci Excel  
  
1.  Proměnné přiřadíte vlastnosti předdefinované dokumentu.  
  
     [!code-vb[Trin_VstcoreProgramming#7](../vsto/codesnippet/VisualBasic/Trin_VstcoreProgrammingExcelVB/ThisWorkbook.vb#7)]
     [!code-csharp[Trin_VstcoreProgramming#7](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingExcelCS/ThisWorkbook.cs#7)]  
  
2.  Přírůstek `Revision Number` vlastnost o jednu.  
  
     [!code-vb[Trin_VstcoreProgramming#8](../vsto/codesnippet/VisualBasic/Trin_VstcoreProgrammingExcelVB/ThisWorkbook.vb#8)]
     [!code-csharp[Trin_VstcoreProgramming#8](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingExcelCS/ThisWorkbook.cs#8)]  
  
## <a name="setting-document-properties-in-word"></a>Nastavení vlastností dokumentu v aplikaci Word  
 Chcete-li pracovat s předdefinované vlastnosti v aplikaci Word, použijte následující vlastnosti:  
  
-   V projektech na úrovni dokumentu, použijte <xref:Microsoft.Office.Tools.Word.Document.BuiltInDocumentProperties%2A> vlastnost `ThisDocument` třídy.  
  
-   V projektu doplňku VSTO, pomocí <xref:Microsoft.Office.Interop.Word._Document.BuiltInDocumentProperties%2A> vlastnost <xref:Microsoft.Office.Interop.Word.Document> objektu.  
  
 Tyto vlastnosti vrátit <xref:Microsoft.Office.Core.DocumentProperties> objekt, který je kolekce z <xref:Microsoft.Office.Core.DocumentProperty> objekty. Můžete použít `Item` vlastnosti kolekce pro načtení určité vlastnosti, pomocí názvu nebo podle indexu v kolekci.  
  
 Následující příklad kódu ukazuje, jak změnit integrované **subjektu** vlastnosti v projektech na úrovni dokumentu.  
  
#### <a name="to-change-the-subject-property"></a>Chcete-li změnit vlastnost předmětu  
  
1.  Proměnné přiřadíte vlastnosti předdefinované dokumentu.  
  
     [!code-csharp[Trin_VstcoreProgrammingWord#1](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingWordCS/ThisDocument.cs#1)]
     [!code-vb[Trin_VstcoreProgrammingWord#1](../vsto/codesnippet/VisualBasic/Trin_VstcoreProgrammingWordVB/ThisDocument.vb#1)]  
  
2.  Změna `Subject` vlastnost "Dokumentu White Paper".  
  
     [!code-csharp[Trin_VstcoreProgrammingWord#2](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingWordCS/ThisDocument.cs#2)]
     [!code-vb[Trin_VstcoreProgrammingWord#2](../vsto/codesnippet/VisualBasic/Trin_VstcoreProgrammingWordVB/ThisDocument.vb#2)]  
  
## <a name="robust-programming"></a>Robustní programování  
 V příkladech se předpokládá, že jste kód napsali `ThisWorkbook` – třída v projektech na úrovni dokumentu pro Excel a `ThisDocument` – třída v projektech na úrovni dokumentu ve Wordu.  
  
 I když pracujete s aplikací Word a Excel a jejich objekty, Microsoft Office poskytuje seznam vlastností, k dispozici integrované dokumentu. Probíhá pokus o přístup k Nedefinovaná vlastnost vyvolá výjimku.  
  
## <a name="see-also"></a>Viz také  
 [Programování doplňků VSTO](../vsto/programming-vsto-add-ins.md)   
 [Programování přizpůsobení na úrovni dokumentu](../vsto/programming-document-level-customizations.md)   
 [Postupy: vytváření a změny přizpůsobených vlastností dokumentu](../vsto/how-to-create-and-modify-custom-document-properties.md)  
  
  