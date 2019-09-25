---
title: NamedRange – ovládací prvek
ms.date: 02/02/2017
ms.topic: conceptual
f1_keywords:
- VST.Toolbox.Range
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- ranges, named
- NamedRange control, events
- NamedRange control, data binding
- NamedRange control
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: e2b5b5d246e1033148bc199da6e7d2bdfb7aa9b3
ms.sourcegitcommit: e98db44f3a33529b0ba188d24390efd09e548191
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/25/2019
ms.locfileid: "71254717"
---
# <a name="namedrange-control"></a>NamedRange – ovládací prvek
  <xref:Microsoft.Office.Tools.Excel.NamedRange> Ovládací prvek je rozsah, který má jedinečný název, zpřístupňuje události a může být svázán s daty. Další informace najdete v tématu [přehled modelu objektů aplikace Excel](../vsto/excel-object-model-overview.md).

 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]

## <a name="create-the-control"></a>Vytvoření ovládacího prvku
 Ovládací prvky můžete <xref:Microsoft.Office.Tools.Excel.NamedRange> přidat do listu aplikace systém Microsoft Office Excel v době návrhu nebo v době běhu v projektech na úrovni dokumentu.

 V doplňku <xref:Microsoft.Office.Tools.Excel.NamedRange> VSTO můžete do listu přidat ovládací prvky v době běhu. Další informace najdete v tématu [jak: Přidejte ovládací prvky NamedRange do](../vsto/how-to-add-namedrange-controls-to-worksheets.md)listů.

> [!NOTE]
> Ve výchozím nastavení se dynamicky vytvořené pojmenované rozsahy neukládají v listu jako hostitelské ovládací prvky při zavření listu. Další informace najdete v tématu [Přidání ovládacích prvků do dokumentů Office v době běhu](../vsto/adding-controls-to-office-documents-at-run-time.md).

 <xref:Microsoft.Office.Tools.Excel.NamedRange>ovládací prvky mohou obsahovat pouze rozsahy na konkrétních listech. <xref:Microsoft.Office.Tools.Excel.NamedRange>ovládací prvky nemohou mít relativní názvy, které se vztahují na všechny listy a nesmí se skládat z rozsahů, které jsou v sešitu rozloženy na dva nebo více listů (3D oblasti).

## <a name="bind-data-to-the-control"></a>Vázání dat k ovládacímu prvku
 Pojmenovaný rozsah by byl dobrým kandidátem na složitou datovou vazbu, protože může mít mnoho buněk. Rozsah je však pouze kolekcí buněk, které nelze snadno namapovat na konkrétní sloupec z datové sady. <xref:Microsoft.Office.Tools.Excel.NamedRange> Proto ovládací prvky podporují pouze jednoduché datové vazby. <xref:Microsoft.Office.Tools.Excel.ListObject> Ovládací prvek lze použít pro složitou datovou vazbu. Další informace naleznete v tématu [ListObject Control](../vsto/listobject-control.md).

 Ovládací prvek může být svázán se zdrojem dat <xref:System.Windows.Forms.Control.DataBindings%2A> pomocí vlastností. <xref:Microsoft.Office.Tools.Excel.NamedRange> Výchozí vlastnost <xref:Microsoft.Office.Tools.Excel.NamedRange> datové vazby ovládacího prvku je <xref:Microsoft.Office.Tools.Excel.NamedRange.Value2%2A>.

 Pokud jsou data v vázané datové sadě aktualizována prostřednictvím libovolného mechanismu, <xref:Microsoft.Office.Tools.Excel.NamedRange> ovládací prvek tyto změny odráží.

## <a name="formatting"></a>Formátování
 Formátování, které lze použít na objekt <xref:Microsoft.Office.Interop.Excel.Range> , lze použít <xref:Microsoft.Office.Tools.Excel.NamedRange> pro ovládací prvek. To zahrnuje ohraničení, písma, formáty čísel a styly.

## <a name="rename-the-control"></a>Přejmenování ovládacího prvku
 Když přidáte <xref:Microsoft.Office.Tools.Excel.NamedRange> ovládací prvek do listu ze **sady nástrojů, sada**Visual Studio automaticky vygeneruje název ovládacího prvku. Název můžete změnit v okně **vlastnosti** .

## <a name="events"></a>Události
 Pro <xref:Microsoft.Office.Tools.Excel.NamedRange> ovládací prvek jsou k dispozici následující události:

- <xref:Microsoft.Office.Tools.Excel.NamedRange.BeforeDoubleClick>

- <xref:Microsoft.Office.Tools.Excel.NamedRange.BeforeRightClick>

- <xref:Microsoft.Office.Tools.Excel.NamedRange.BindingContextChanged>

- <xref:Microsoft.Office.Tools.Excel.NamedRange.Change>

- <xref:Microsoft.Office.Tools.Excel.NamedRange.Deselected>

- <xref:System.ComponentModel.Component.Disposed>

- <xref:Microsoft.Office.Tools.Excel.NamedRange.Selected>

- <xref:Microsoft.Office.Tools.Excel.NamedRange.SelectionChange>

## <a name="see-also"></a>Viz také:
- [Automatizace aplikace Excel s použitím rozšířených objektů](../vsto/automating-excel-by-using-extended-objects.md)
- [Ukázky a návody pro vývoj pro Office](../vsto/office-development-samples-and-walkthroughs.md)
- [Vázání dat k ovládacím prvkům v řešeních pro systém Office](../vsto/binding-data-to-controls-in-office-solutions.md)
- [Rozšiřování dokumentů aplikace Word a excelových sešitů v doplňcích VSTO za běhu](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)
- [Ovládací prvky v dokumentech Office](../vsto/controls-on-office-documents.md)
- [Přidání ovládacích prvků do dokumentů Office v době běhu](../vsto/adding-controls-to-office-documents-at-run-time.md)
- [Postupy: Přidání ovládacích prvků NamedRange do listů](../vsto/how-to-add-namedrange-controls-to-worksheets.md)
- [Postupy: Změna velikosti ovládacích prvků NamedRange](../vsto/how-to-resize-namedrange-controls.md)
- [Vázání dat k ovládacím prvkům v řešeních pro systém Office](../vsto/binding-data-to-controls-in-office-solutions.md)
- [Návod: Program pro události ovládacího prvku NamedRange](../vsto/walkthrough-programming-against-events-of-a-namedrange-control.md)
- [Programové omezení hostitelských položek a hostitelských ovládacích prvků](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)
