---
title: Vlastnosti v projektech Office | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Trust Assemblies Location property
- Cache in Document property
- properties [Office development in Visual Studio]
- Namespace for Host Item property
- Office projects [Office development in Visual Studio], properties
- projects [Office development in Visual Studio], properties
- Value2 property
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 47af1dae914528a3a338503989e53f081dfffde5
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="properties-in-office-projects"></a>Vlastnosti v projektech pro systém Office
  Nejsou k dispozici několik důležitých vlastnosti, které jsou k dispozici pro projekty Office v sadě Visual Studio. Tyto vlastnosti jsou přístupné z **vlastnosti** okno.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
## <a name="namespace-for-host-item"></a>Namespace pro hostitelskou položku  
 Použití **Namespace pro hostitelskou položku** vlastnost změnit obor názvů pro hostitele tříd položek (například `ThisAddIn`, `ThisWorkbook`, nebo `ThisDocument` třídy) v projektech Visual C#. Tato vlastnost se zobrazí v **vlastnosti** okno když vyberete uzel dokumentu v projektech na úrovni dokumentu (například ExcelWorkbook1.xlsx nebo WordDocument1.docx) nebo uzlu aplikace v projektu doplňku VSTO (například aplikace Excel nebo Word ) v **Průzkumníku řešení**.  
  
 Když vytvoříte projekt Visual C# Office, hostitelské položky jsou udělená oboru názvů založeného na název projektu. Je doporučeno používat **Namespace pro hostitelskou položku** vlastnost změnit obor názvů, nikoli kód upravit soubory přímo. Použijete-li tuto vlastnost, obor názvů se změní v souborech generovaný kód (skryté), a také v souborech viditelné kódu.  
  
## <a name="cacheindocument"></a>CacheInDocument  
 **CacheInDocument** vlastnost se zobrazí v **vlastnosti** okna pro projekty na úrovni dokumentu při výběru instance <xref:System.Data.DataSet> v návrháři Visual Studio. Můžete uložit do mezipaměti pouze veřejné členy; Ujistěte se, že **modifikátory** je nastavena na **veřejné** Pokud chcete do mezipaměti <xref:System.Data.DataSet>.  
  
 Tato vlastnost nabývá logických hodnot:  
  
-   Vyberte **true** pro ukládání do mezipaměti datovou sadu v dokumentu.  
  
-   Vyberte **false** Pokud nechcete, aby datové sady do mezipaměti v dokumentu.  
  
 Další informace o ukládání dat do mezipaměti najdete v tématu [Data do mezipaměti v přizpůsobeních na úrovni dokumentu](../vsto/cached-data-in-document-level-customizations.md).  
  
## <a name="value2"></a>Value2  
 **Value2** vlastnost je dostupná jenom pro projekty sešitu nebo šablony aplikace Excel. Zobrazí se pod **datové vazby** uzel vlastnosti v **vlastnosti** okno při výběru <xref:Microsoft.Office.Tools.Excel.NamedRange> ovládací prvek v Návrháři listu.  
  
 Použití **Value2** vlastnost v **vlastnosti** okno vytvořit vazbu <xref:Microsoft.Office.Tools.Excel.NamedRange.Value2%2A> vlastnost <xref:Microsoft.Office.Tools.Excel.NamedRange> pole ve zdroji dat.  
  
## <a name="see-also"></a>Viz také  
 [Návrh a vytváření řešení pro systém Office](../vsto/designing-and-creating-office-solutions.md)   
 [Přehled šablon projektů Microsoft Office](../vsto/office-project-templates-overview.md)   
 [Události v projektech pro systém Office](../vsto/events-in-office-projects.md)  
  
  