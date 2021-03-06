---
title: 'Postupy: přidávání obrazců do dokumentů aplikace Visio prostřednictvím kódu programu'
titleSuffix: ''
ms.date: 02/02/2017
ms.topic: how-to
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Visio [Office development in Visual Studio], adding Visio shapes
- shapes [Office development in Visual Studio], adding Visio shapes
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: e8eb3ad837f699a1bb0bbc327b6e892a20866e0a
ms.sourcegitcommit: 9d2829dc30b6917e89762d602022915f1ca49089
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/30/2020
ms.locfileid: "91584227"
---
# <a name="how-to-programmatically-add-shapes-to-a-visio-document"></a>Postupy: přidávání obrazců do dokumentů aplikace Visio prostřednictvím kódu programu
  Systém Microsoft Office do dokumentu aplikace Visio lze přidat tvary načtením předloh ze vzorníku a přetažením obrazců na aktivní stránce.

 Další informace najdete v referenční dokumentaci k jazyku VBA pro [Microsoft.Office.Interop.Visio.Documents. Přidejte](/office/vba/api/Visio.Documents.Add) metodu, vlastnost [Microsoft. Office. Interop. Visio. Application. ActivePage](/office/vba/api/Visio.Application.ActivePage) a metodu [Microsoft. Office. Interop. Visio. Page. drop](/office/vba/api/Visio.Page.Drop) .

## <a name="add-shapes-to-a-visio-document"></a>Přidání obrazců do dokumentu Visia

### <a name="to-add-shapes-to-a-visio-document"></a>Přidání obrazců do dokumentu aplikace Visio

- Když je dokument aktivní, načtěte z kolekce Documents. Masters šablony a přetáhněte je na aktivní dokument. Hlavní stránku můžete načíst pomocí názvu indexu nebo předlohy.

     Následující příklad kódu vytvoří prázdný dokument Visia a pak ho otevře se vzorníkem **základní tvary** s ukotveným. Kód potom načte několik tvarů a obnoví je na aktivní stránce.

     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#13](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#13)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#13](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#13)]

## <a name="see-also"></a>Viz také
- [Řešení aplikace Visio](../vsto/visio-solutions.md)
- [Přehled modelu objektů aplikace Visio](../vsto/visio-object-model-overview.md)
- [Práce s obrazci aplikace Visio](../vsto/working-with-visio-shapes.md)
- [Postupy: kopírování a vkládání tvarů v dokumentu aplikace Visio prostřednictvím kódu programu](../vsto/how-to-programmatically-copy-and-paste-shapes-in-a-visio-document.md)
