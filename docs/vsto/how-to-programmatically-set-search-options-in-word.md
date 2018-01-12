---
title: "Postupy: nastavování možností hledání v aplikaci Word | Microsoft Docs"
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
- settings, Word search options
- documents [Office development in Visual Studio], search options
- Word, searching options
- searching, Word options
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: fa575f8c89e9aea125179c896c35b8ecc775965e
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-programmatically-set-search-options-in-word"></a>Postupy: Nastavování možností hledání v aplikaci Word prostřednictvím kódu programu
  Existují dva způsoby, jak nastavit možnosti vyhledávání pro výběr v dokumentech aplikace Microsoft Office Word:  
  
-   Nastavit jednotlivé vlastnosti <xref:Microsoft.Office.Interop.Word.Find> objektu.  
  
-   Použít argumenty <xref:Microsoft.Office.Interop.Word.Find.Execute%2A> metodu <xref:Microsoft.Office.Interop.Word.Find> objektu.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
## <a name="using-properties-of-a-find-object"></a>Pomocí vlastnosti objektu najít  
 Následující kód nastaví vlastnosti <xref:Microsoft.Office.Interop.Word.Find> objekt, který chcete hledat text v aktuálním výběru. Všimněte si, že kritéria hledání, jako je například vyhledávání předání, zabalení a text pro vyhledávání, jsou vlastnosti <xref:Microsoft.Office.Interop.Word.Find> objektu.  
  
 Nastavení těchto vlastností <xref:Microsoft.Office.Interop.Word.Find> objekt není užitečné při psaní kódu jazyka C# vzhledem k tomu, že musíte zadat stejné vlastnosti jako parametry <xref:Microsoft.Office.Interop.Word.Find.Execute%2A> metoda. Proto tento příklad obsahuje pouze kód jazyka Visual Basic.  
  
#### <a name="to-set-search-options-using-a-find-object"></a>Chcete-li nastavit možnosti hledání pomocí objektu najít  
  
1.  Nastavit vlastnosti <xref:Microsoft.Office.Interop.Word.Find> objektu k vyhledání předat prostřednictvím výběr text **mi najít**.  
  
     [!code-vb[Trin_VstcoreWordAutomation#76](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#76)]  
  
## <a name="using-execute-method-arguments"></a>Pomocí provést argumenty – metoda  
 Následující kód používá <xref:Microsoft.Office.Interop.Word.Find.Execute%2A> metodu <xref:Microsoft.Office.Interop.Word.Find> objekt, který chcete hledat text v aktuálním výběru. Všimněte si, že kritéria hledání, jako je například vyhledávání předání, zabalení a text pro vyhledávání, jsou předány jako parametry <xref:Microsoft.Office.Interop.Word.Find.Execute%2A> metoda.  
  
#### <a name="to-set-search-options-using-execute-method-arguments"></a>Nastavení možností vyhledávání pomocí argumenty Execute – metoda  
  
1.  Jako parametry předat kritéria vyhledávání <xref:Microsoft.Office.Interop.Word.Find.Execute%2A> metody na hledání předat prostřednictvím výběr text **mi najít**.  
  
     [!code-vb[Trin_VstcoreWordAutomation#77](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#77)]
     [!code-csharp[Trin_VstcoreWordAutomation#77](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#77)]  
  
## <a name="see-also"></a>Viz také  
 [Postupy: hledání prostřednictvím kódu programu a nahrazení textu v dokumentech](../vsto/how-to-programmatically-search-for-and-replace-text-in-documents.md)   
 [Postupy: procházení nalezených položek v dokumentech prostřednictvím kódu programu cykly](../vsto/how-to-programmatically-loop-through-found-items-in-documents.md)   
 [Postupy: Obnovení výběru po hledání prostřednictvím kódu programu](../vsto/how-to-programmatically-restore-selections-after-searches.md)  
  
  