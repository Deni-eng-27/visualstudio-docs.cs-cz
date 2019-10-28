---
title: Ovládací prvek XmlMappedRange –
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- XMLMappedRange control, data binding
- XMLMappedRange control
- XMLMappedRange control, events
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 01417d9c08491edc882f7f758bb36e6184500e52
ms.sourcegitcommit: dcbb876a5dd598f2538e62e1eabd4dc98595b53a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/28/2019
ms.locfileid: "72985364"
---
# <a name="xmlmappedrange-control"></a>Ovládací prvek XmlMappedRange –
  <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> ovládací prvek je rozsah, který je vytvořen pouze v případě, že je neopakující se prvek schématu mapován na buňku v aplikaci systém Microsoft Office Excel. Například pokud atribut `maxOccurs` elementu Schema se rovná 1. Poté, co aplikace Visual Studio vytvoří rozsah mapovaného kódu XML, lze naprogramovat přímo bez nutnosti procházení objektového modelu aplikace Excel. Ovládací prvek <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> lze odstranit pouze v aplikaci Excel, pokud je odebráno mapování elementu.

 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]

## <a name="bind-data-to-the-control"></a>Vázání dat k ovládacímu prvku
 Ovládací prvek <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> podporuje vazbu s jedním datovým polem (jednoduchou datovou vazbu). Ovládací prvek <xref:Microsoft.Office.Tools.Excel.ListObject> může podporovat složitou datovou vazbu a je automaticky vytvořen při mapování opakujícího se elementu schématu na buňku. Další informace naleznete v tématu [ListObject Control](../vsto/listobject-control.md).

 Ovládací prvek <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> je svázán se zdrojem dat pomocí vlastnosti <xref:System.Windows.Forms.Control.DataBindings%2A>. Když je do buňky listu přidána <xref:Microsoft.Office.Tools.Excel.XmlMappedRange>, sada Visual Studio automaticky vygeneruje datovou sadu z dat v mapovaných buňkách a naváže ovládací prvek na tuto datovou sadu. Výchozí vlastnost datové vazby <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> je <xref:Microsoft.Office.Tools.Excel.XmlMappedRange.Value2%2A>.

 Pokud jsou data v vázané datové sadě aktualizována prostřednictvím libovolného mechanismu, ovládací prvek <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> odráží změny.

## <a name="formatting"></a>Formátování
 Můžete použít stejné formátování <xref:Microsoft.Office.Tools.Excel.XmlMappedRange>mu ovládacímu prvku, který můžete použít na <xref:Microsoft.Office.Interop.Excel.Range>. To zahrnuje ohraničení, písma, formát čísel a styly.

## <a name="events"></a>Události
 K dispozici jsou události pro ovládací prvek <xref:Microsoft.Office.Tools.Excel.XmlMappedRange>:

- <xref:Microsoft.Office.Tools.Excel.XmlMappedRange.BeforeDoubleClick>

- <xref:Microsoft.Office.Tools.Excel.XmlMappedRange.BeforeRightClick>

- <xref:Microsoft.Office.Tools.Excel.XmlMappedRange.BindingContextChanged>

- <xref:Microsoft.Office.Tools.Excel.XmlMappedRange.Change>

- <xref:Microsoft.Office.Tools.Excel.XmlMappedRange.Selected>

- <xref:Microsoft.Office.Tools.Excel.XmlMappedRange.Deselected>

- <xref:System.ComponentModel.Component.Disposed>

- <xref:Microsoft.Office.Tools.Excel.XmlMappedRange.SelectionChange>

## <a name="see-also"></a>Viz také:
- [Automatizace Excelu pomocí rozšířených objektů](../vsto/automating-excel-by-using-extended-objects.md)
- [Postupy: Přidání ovládacích prvků XmlMappedRange – do listů](../vsto/how-to-add-xmlmappedrange-controls-to-worksheets.md)
- [Vázání dat k ovládacím prvkům v řešeních pro systém Office](../vsto/binding-data-to-controls-in-office-solutions.md)
- [Postupy: mapování schémat na listy v rámci sady Visual Studio](../vsto/how-to-map-schemas-to-worksheets-inside-visual-studio.md)
- [Programové omezení hostitelských položek a hostitelských ovládacích prvků](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)
