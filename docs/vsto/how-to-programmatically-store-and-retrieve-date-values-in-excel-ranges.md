---
title: Store & načtení hodnot data do oblastí aplikace Excel prostřednictvím kódu programu
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Excel [Office development in Visual Studio], retrieving date values from ranges
- ranges, retrieving data values
- dates, retrieving from Excel ranges
- Excel [Office development in Visual Studio], storing date values in ranges
- date values, storing in Excel ranges
- dates, storing in Excel ranges
- ranges, storing date values
- date values
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: d855ffd91ccdc07a2d69401d7a8611175cc60941
ms.sourcegitcommit: 7eb2fb21805d92f085126f3a820ac274f2216b4e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/22/2019
ms.locfileid: "67328924"
---
# <a name="how-to-programmatically-store-and-retrieve-date-values-in-excel-ranges"></a>Postupy: Programově ukládání a načítání hodnot data do oblastí aplikace Excel
  Můžete ukládat a načítat hodnoty v <xref:Microsoft.Office.Tools.Excel.NamedRange> ovládací prvek nebo rozsah objekt nativní aplikace Excel.

 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]

 Pokud uložíte hodnotu data, která nebo po 1/1/1900 v rozsahu pomocí nástroje pro vývoj pro Office v sadě Visual Studio, je uložen ve formátu OLE Automation (OA). Je nutné použít <xref:System.DateTime.FromOADate%2A> metody k načtení hodnoty data OLE Automation (OA). Pokud je datum starší než 1/1/1900, uloží se jako řetězec.

> [!NOTE]
> Data aplikace Excel se liší od data OLE Automation na prvních dvou měsíců 1900. Existují také rozdíly pokud **1904 datum systému** zaškrtnutá možnost. Následující příklady kódu se nezabývají tyto rozdíly.

## <a name="use-a-namedrange-control"></a>Použití ovládacího prvku NamedRange

- Tento příklad je určený pro přizpůsobení na úrovni dokumentu. Následující kód musí být umístěn ve třídě list, není v `ThisWorkbook` třídy.

### <a name="to-store-a-date-value-in-a-named-range"></a>K uložení hodnoty datum v pojmenované oblasti

1. Vytvoření <xref:Microsoft.Office.Tools.Excel.NamedRange> ovládacího prvku v buňce **A1**.

     [!code-csharp[Trin_VstcoreExcelAutomation#50](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#50)]
     [!code-vb[Trin_VstcoreExcelAutomation#50](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#50)]

2. Nastavit jako hodnotu pro dnešní datum `NamedRange1`.

     [!code-csharp[Trin_VstcoreExcelAutomation#51](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#51)]
     [!code-vb[Trin_VstcoreExcelAutomation#51](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#51)]

### <a name="to-retrieve-a-date-value-from-a-named-range"></a>Načíst hodnotu data z pojmenované oblasti

1. Načíst hodnotu data z `NamedRange1`.

     [!code-csharp[Trin_VstcoreExcelAutomation#52](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#52)]
     [!code-vb[Trin_VstcoreExcelAutomation#52](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#52)]

## <a name="use-native-excel-ranges"></a>Použít nativní oblastí aplikace Excel

### <a name="to-store-a-date-value-in-a-native-excel-range-object"></a>K uložení hodnoty datum v rozsahu objektu nativní aplikace Excel

1. Vytvoření <xref:Microsoft.Office.Interop.Excel.Range> , který představuje buňku **A1**.

     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#25](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#25)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#25](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#25)]

2. Nastavit jako hodnotu pro dnešní datum `rng`.

     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#26](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#26)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#26](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#26)]

### <a name="to-retrieve-a-date-value-from-a-native-excel-range-object"></a>Načíst hodnotu data z nativní objektu Excelového rozsahu

1. Načíst hodnotu data z `rng`.

     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#27](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#27)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#27](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#27)]

## <a name="see-also"></a>Viz také:
- [Práce s oblastmi](../vsto/working-with-ranges.md)
- [Přehled modelu objektů aplikace Excel](../vsto/excel-object-model-overview.md)
- [Namedrange – ovládací prvek](../vsto/namedrange-control.md)
- [Postupy: Odkazování na oblasti listů v kódu programu](../vsto/how-to-programmatically-refer-to-worksheet-ranges-in-code.md)
- [Postupy: Přidání ovládacích prvků NamedRange do listů](../vsto/how-to-add-namedrange-controls-to-worksheets.md)
- [Volitelné parametry v řešeních pro systém Office](../vsto/optional-parameters-in-office-solutions.md)
