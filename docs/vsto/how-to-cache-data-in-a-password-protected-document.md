---
title: 'Postupy: mezipaměti Data v dokumentu chráněném heslem | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data caching [Office development in Visual Studio], protected documents
- datasets [Office development in Visual Studio], caching
- data [Office development in Visual Studio], caching
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 71ce65cd253ea6473a07a98542449a1e47ae9d7c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-cache-data-in-a-password-protected-document"></a>Postupy: Ukládání dat do mezipaměti v dokumentu chráněném heslem
  Pokud přidáte data do mezipaměti data v dokumentu nebo sešitu, který je chráněný heslem, změny data uložená v mezipaměti nejsou uloženy automaticky. Změny můžete uložit data uložená v mezipaměti přepsáním dvě metody ve vašem projektu.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
## <a name="caching-in-word-documents"></a>Ukládání do mezipaměti v dokumentech aplikace Word  
  
#### <a name="to-cache-data-in-a-word-document-that-is-protected-with-a-password"></a>Ukládat data do mezipaměti v dokumentu aplikace Word, který je chráněný heslem  
  
1.  V `ThisDocument` třídy, označte veřejné pole nebo vlastnost ukládat do mezipaměti. Další informace najdete v tématu [ukládání dat do mezipaměti](../vsto/caching-data.md).  
  
2.  Přepsání <xref:Microsoft.Office.Tools.Word.DocumentBase.UnprotectDocument%2A> metoda v `ThisDocument` třídy a odebrání ochrany dokumentu.  
  
     Při ukládání dokumentu [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] volá tuto metodu tak, abyste získali příležitost ke zrušení ochrany dokumentu. To umožňuje uložení změn dat v mezipaměti.  
  
3.  Přepsání <xref:Microsoft.Office.Tools.Word.DocumentBase.ProtectDocument%2A> metoda v `ThisDocument` třídy a znovu nastavit ochranu dokumentu.  
  
     Po uložení dokumentu [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] volá tuto metodu tak, abyste získali příležitost k opětovnému použití ochrany v dokumentu.  
  
### <a name="example"></a>Příklad  
 Následující příklad kódu ukazuje, jak pro ukládání do mezipaměti data v dokumentu aplikace Word, který je chráněný heslem. Předtím, než kód odebere ochranu v <xref:Microsoft.Office.Tools.Word.DocumentBase.UnprotectDocument%2A> metoda, uloží aktuální <xref:Microsoft.Office.Tools.Word.Document.ProtectionType%2A> hodnoty, aby znovu stejný typ ochrany může být použit v <xref:Microsoft.Office.Tools.Word.DocumentBase.ProtectDocument%2A> metoda.  
  
 [!code-csharp[Trin_CachedDataProtectedDocument#1](../vsto/codesnippet/CSharp/Trin_CachedDataProtectedDocument/ThisDocument.cs#1)]
 [!code-vb[Trin_CachedDataProtectedDocument#1](../vsto/codesnippet/VisualBasic/Trin_CachedDataProtectedDocument/ThisDocument.vb#1)]  
  
### <a name="compiling-the-code"></a>Probíhá kompilace kódu  
 Přidejte tento kód, který `ThisDocument` třídy ve vašem projektu. Tento kód předpokládá, že je heslo uloženo do pole s názvem `securelyStoredPassword`.  
  
## <a name="caching-in-excel-workbooks"></a>Ukládání do mezipaměti v sešitech aplikace Excel  
 Projekty aplikace Excel, tento postup je nezbytný, jenom v případě, že budete chránit celý sešit s heslem pomocí <xref:Microsoft.Office.Tools.Excel.Workbook.Protect%2A> metoda. Tento postup není nutný, pokud budete chránit pouze konkrétní listu s heslem pomocí <xref:Microsoft.Office.Tools.Excel.Worksheet.Protect%2A> metoda.  
  
#### <a name="to-cache-data-in-an-excel-workbook-that-is-protected-with-a-password"></a>Ukládat data do mezipaměti v sešitu aplikace Excel, který je chráněný heslem  
  
1.  V `ThisWorkbook` třídy nebo některé z `Sheet` *n* třídy, označte veřejné pole nebo vlastnost ukládat do mezipaměti. Další informace najdete v tématu [ukládání dat do mezipaměti](../vsto/caching-data.md).  
  
2.  Přepsání <xref:Microsoft.Office.Tools.Excel.WorkbookBase.UnprotectDocument%2A> metoda v `ThisWorkbook` třídy a odebrat ochranu ze sešitu.  
  
     Když je sešit uložit, [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] volá tuto metodu tak, abyste získali příležitost ochranu sešitu. To umožňuje uložení změn dat v mezipaměti.  
  
3.  Přepsání <xref:Microsoft.Office.Tools.Excel.WorkbookBase.ProtectDocument%2A> metoda v `ThisWorkbook` třídy a znovu nastavit ochranu dokumentu.  
  
     Po uložení sešitu [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] volá tuto metodu tak, abyste získali příležitost k opětovnému použitá ochranu sešitu.  
  
### <a name="example"></a>Příklad  
 Následující příklad kódu ukazuje, jak pro ukládání do mezipaměti data v sešitu aplikace Excel, který je chráněný heslem. Předtím, než ochranu v odebere kód <xref:Microsoft.Office.Tools.Excel.WorkbookBase.UnprotectDocument%2A> metoda, uloží aktuální <xref:Microsoft.Office.Tools.Excel.Workbook.ProtectStructure%2A> a <xref:Microsoft.Office.Tools.Excel.Workbook.ProtectWindows%2A> hodnoty, aby znovu stejný typ ochrany může být použit v <xref:Microsoft.Office.Tools.Excel.WorkbookBase.ProtectDocument%2A> metoda.  
  
 [!code-vb[Trin_CachedDataProtectedWorkbook#1](../vsto/codesnippet/VisualBasic/Trin_CachedDataProtectedWorkbook/ThisWorkbook.vb#1)]
 [!code-csharp[Trin_CachedDataProtectedWorkbook#1](../vsto/codesnippet/CSharp/Trin_CachedDataProtectedWorkbook/ThisWorkbook.cs#1)]  
  
### <a name="compiling-the-code"></a>Probíhá kompilace kódu  
 Přidejte tento kód, který `ThisWorkbook` třídy ve vašem projektu. Tento kód předpokládá, že je heslo uloženo do pole s názvem `securelyStoredPassword`.  
  
## <a name="see-also"></a>Viz také  
 [Ukládání dat do mezipaměti](../vsto/caching-data.md)   
 [Postupy: ukládat Data do mezipaměti pro použití v režimu Offline nebo na serveru](../vsto/how-to-cache-data-for-use-offline-or-on-a-server.md)   
 [Postupy: Ukládání zdroje dat v dokumentu systému Office do mezipaměti prostřednictvím kódu programu](../vsto/how-to-programmatically-cache-a-data-source-in-an-office-document.md)  
  
  