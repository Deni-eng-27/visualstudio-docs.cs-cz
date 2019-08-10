---
title: Objekt VSTextView | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- VSTextView
helpviewer_keywords:
- VSTextView object, reference
- views [Visual Studio SDK], reference
ms.assetid: 78272ddc-9718-4c65-a94e-a44a2e8d54f4
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a5d3983dcefd515a43d573166c9bd772fd23bf0a
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68924159"
---
# <a name="vstextview-object"></a>Objekt VSTextView
Textové zobrazení je okno, které umožňuje uživatelům zobrazit a upravit textovou vyrovnávací paměť textu v kódu Unicode. V podstatě se jedná o to, co většina uživatelů na Editor odkazuje. Vzhledem k tomu, že je zobrazení odděleno od vyrovnávací paměti různými textovými vrstvami (zalamování řádků, text sbalení a tak dále), není zaručeno, že zobrazení je přesná reprezentace textu ve vyrovnávací paměti. Další informace o zobrazení textu najdete v tématu [přístup k zobrazení TheText pomocí starší verze rozhraní API](../extensibility/accessing-thetext-view-by-using-the-legacy-api.md).

 V následující tabulce jsou uvedena rozhraní v <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextView> objektu.

|Rozhraní|Popis|
|---------------|-----------------|
|[IDropSource](/windows/desktop/api/oleidl/nn-oleidl-idropsource)|Standardní rozhraní OLE.|
|<xref:Microsoft.VisualStudio.OLE.Interop.IDropTarget>|Standardní rozhraní OLE.|
|<xref:Microsoft.VisualStudio.OLE.Interop.IObjectWithSite>|Standardní rozhraní OLE.|
|<xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>|Standardní rozhraní OLE.|
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsCompoundAction>|Umožňuje vytváření složených akcí (tj. akcí, které jsou seskupeny v jedné jednotce zpět/znovu).|
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView>|Poskytuje základní metody pro správu a přístup k zobrazení. `IVsTextView`není bezpečný pro přístup z více vláken.|
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowPane>|Vytvoří a spravuje podokno okna.|
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsLayeredTextView>|Komunikuje s vrstvami textu.|
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsThreadSafeTextView>|Provádí operace v zobrazení z jiného vlákna.|

## <a name="see-also"></a>Viz také:
- [Úpravy obrázků](https://www.microsoft.com/download/details.aspx?id=55984)
- [Objekt VSTextBuffer](../extensibility/vstextbuffer-object.md)
- [Přístup k zobrazení theText pomocí starší verze rozhraní API](../extensibility/accessing-thetext-view-by-using-the-legacy-api.md)