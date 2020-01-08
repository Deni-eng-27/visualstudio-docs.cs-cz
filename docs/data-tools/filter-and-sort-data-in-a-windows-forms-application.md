---
title: Filtrování a řazení dat ve formulářové aplikaci Windows
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- row states, filtering
- data views, sorting
- row version, filtering
- row states
- data views, filtering
- sorting datasets, using data views
- dataset filtering, using data views
ms.assetid: f4f100f1-776d-46dc-b2fd-5b35b98d9561
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: 596397cc22cf0f0134463256c0861127dcfb81e1
ms.sourcegitcommit: d233ca00ad45e50cf62cca0d0b95dc69f0a87ad6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/01/2020
ms.locfileid: "75586611"
---
# <a name="filter-and-sort-data-in-a-windows-forms-application"></a>Filtrování a řazení dat ve formulářové aplikaci Windows

Data filtrujete nastavením vlastnosti <xref:System.Windows.Forms.BindingSource.Filter%2A> na řetězcový výraz, který vrací požadované záznamy.

Data řadíte nastavením vlastnosti <xref:System.Windows.Forms.BindingSource.Sort%2A> na název sloupce, podle kterého chcete řadit; Přidejte `DESC` pro řazení v sestupném pořadí nebo přidejte `ASC` k řazení ve vzestupném pořadí.

> [!NOTE]
> Pokud vaše aplikace nepoužívá <xref:System.Windows.Forms.BindingSource> komponenty, můžete filtrovat a řadit data pomocí objektů <xref:System.Data.DataView>. Další informace naleznete v tématu [DataViews](/dotnet/framework/data/adonet/dataset-datatable-dataview/dataviews).

## <a name="to-filter-data-by-using-a-bindingsource-component"></a>Filtrování dat pomocí komponenty BindingSource

- Vlastnost <xref:System.Windows.Forms.BindingSource.Filter%2A> nastavte na výraz, který chcete vrátit. Například následující kód vrátí zákazníky se `CompanyName`, který začíná "B":

     [!code-csharp[VbRaddataDisplaying#6](../data-tools/codesnippet/CSharp/filter-and-sort-data-in-a-windows-forms-application_1.cs)]
     [!code-vb[VbRaddataDisplaying#6](../data-tools/codesnippet/VisualBasic/filter-and-sort-data-in-a-windows-forms-application_1.vb)]

## <a name="to-sort-data-by-using-a-bindingsource-component"></a>Řazení dat pomocí komponenty BindingSource

- Vlastnost <xref:System.Windows.Forms.BindingSource.Sort%2A> nastavte na sloupec, podle kterého chcete řadit. Například následující kód seřadí zákazníky do sloupce `CompanyName` v sestupném pořadí:

     [!code-csharp[VbRaddataDisplaying#7](../data-tools/codesnippet/CSharp/filter-and-sort-data-in-a-windows-forms-application_2.cs)]
     [!code-vb[VbRaddataDisplaying#7](../data-tools/codesnippet/VisualBasic/filter-and-sort-data-in-a-windows-forms-application_2.vb)]

## <a name="see-also"></a>Viz také:

- [Vytvoření vazby ovládacích prvků k datům v sadě Visual Studio](../data-tools/bind-controls-to-data-in-visual-studio.md)
