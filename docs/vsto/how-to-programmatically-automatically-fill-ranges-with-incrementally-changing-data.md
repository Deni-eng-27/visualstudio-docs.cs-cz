---
title: 'Postupy: Prostřednictvím kódu programu automaticky vyplnit oblastí s přírůstkově se měnícími daty'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Autofill method [Excel]
- filling ranges automatically
- ranges, automatically filling
- workbooks, filling ranges
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: edb3a1bfaad8d662fb51a8527da6bef183fd05c4
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63428174"
---
# <a name="how-to-programmatically-automatically-fill-ranges-with-incrementally-changing-data"></a>Postupy: Prostřednictvím kódu programu automaticky vyplnit oblastí s přírůstkově se měnícími daty
  <xref:Microsoft.Office.Interop.Excel.Range.AutoFill%2A> Metodu <xref:Microsoft.Office.Interop.Excel.Range> objektu umožňuje automaticky vyplnit rozsah v listu s hodnotami. Nejčastěji <xref:Microsoft.Office.Interop.Excel.Range.AutoFill%2A> metoda se používá k ukládání postupně zvýšením nebo snížením hodnoty v rozsahu. Můžete určit chování zadáním volitelné konstanta z <xref:Microsoft.Office.Interop.Excel.XlAutoFillType> výčtu.

 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]

 Při použití, je nutné zadat dvě oblasti <xref:Microsoft.Office.Interop.Excel.Range.AutoFill%2A>:

- Oblast, která volá <xref:Microsoft.Office.Interop.Excel.Range.AutoFill%2A> metodu, která určuje počáteční bod výplně a obsahuje počáteční hodnotu.

- Rozsah, který chcete vyplnit, předán jako parametr <xref:Microsoft.Office.Interop.Excel.Range.AutoFill%2A> metody. Tento cílový rozsah musí obsahovat oblast, která obsahuje počáteční hodnotu.

    > [!NOTE]
    > Nelze předat <xref:Microsoft.Office.Tools.Excel.NamedRange> řízení místo <xref:Microsoft.Office.Interop.Excel.Range>. Další informace najdete v tématu [programová omezení hostitelských položek a hostitelských ovládacích prvků](../vsto/programmatic-limitations-of-host-items-and-host-controls.md).

## <a name="example"></a>Příklad
 [!code-csharp[Trin_VstcoreExcelAutomation#49](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#49)]
 [!code-vb[Trin_VstcoreExcelAutomation#49](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#49)]

## <a name="compile-the-code"></a>Kompilace kódu
 Počáteční hodnota musí obsahovat první buňky rozsahu, který chcete vyplnit.

 V příkladu vyžaduje vyplnění tří oblastí:

- Sloupce B se zahrnou pět dní v týdnu. Pro původní hodnotu zadejte **pondělí** do buňky B1.

- Sloupec C se zahrnou pěti měsíců. Pro původní hodnotu zadejte **ledna** v buňce C1.

- Sloupec D je zahrnují řadu čísla a narůstajících o dvou pro každý řádek. Počáteční hodnoty, zadejte **4** v buňce D1 a **6** v buňce D2.

## <a name="see-also"></a>Viz také:
- [Práce s oblastmi](../vsto/working-with-ranges.md)
- [Postupy: Odkazování na oblasti listů v kódu programu](../vsto/how-to-programmatically-refer-to-worksheet-ranges-in-code.md)
- [Postupy: Používání stylů pro oblasti sešitů prostřednictvím kódu programu](../vsto/how-to-programmatically-apply-styles-to-ranges-in-workbooks.md)
- [Postupy: Spouštění výpočtů v aplikaci Excel](../vsto/how-to-programmatically-run-excel-calculations-programmatically.md)
- [Přehled ovládacích prvků hostitele a hostitelské položky](../vsto/host-items-and-host-controls-overview.md)
- [Volitelné parametry v řešeních pro systém Office](../vsto/optional-parameters-in-office-solutions.md)
