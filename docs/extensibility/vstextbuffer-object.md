---
title: Objekt VSTextBuffer | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- VSTextBuffer
helpviewer_keywords:
- VSTextBuffer object, reference
- views [Visual Studio SDK], VSTextBuffer object
ms.assetid: c5f94b45-7249-4e1f-a53d-1d2a1c61e0ef
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 856a685cbf962f8b26f77932c738c758edcf1f91
ms.sourcegitcommit: 4b29efeb3a5f05888422417c4ee236e07197fb94
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/11/2020
ms.locfileid: "90012188"
---
# <a name="vstextbuffer-object"></a>Objekt VSTextBuffer
Objekt textové vyrovnávací paměti představuje datový proud textu v kódu Unicode, který je obecně spojen se souborem. <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer>Objekt lze použít mimo kontext základního editoru, jako v průvodci.

 V následující tabulce jsou uvedena rozhraní `VSTextBuffer` .

|Metoda|Popis|
|------------|-----------------|
|[IOleCommandTarget –](/windows/desktop/api/docobj/nn-docobj-iolecommandtarget)|Standardní rozhraní OLE. Slouží k vrácení zpět nebo opětovnému zpracování ve vyrovnávací paměti.|
|[IPersistFile](/windows/desktop/api/objidl/nn-objidl-ipersistfile)|Standardní rozhraní OLE.|
|[IPersistStream](/windows/desktop/api/objidl/nn-objidl-ipersiststream)|Standardní rozhraní OLE.|
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsCompoundAction>|Umožňuje vytváření akcí sloučenin (tj. akcí, které jsou seskupeny do jedné jednotky akce zpět/znovu).|
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData>|Umožňuje trvalá data dokumentu spravovaná vyrovnávací pamětí textu.|
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer>|Poskytuje základní služby; používá mnoho klientů.|
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextFind>|Používá se k prohledání vyrovnávací paměti.|
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines>|Poskytuje funkce pro čtení a zápis pomocí dvourozměrných souřadnic. Dědí z `IVsTextBuffer` .|
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextStream>|Poskytuje funkce pro čtení a zápis s použitím jednorozměrné souřadnice. Dědí z `IVsTextBuffer` .|
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextScanner>|Poskytuje rychlý a sekvenční přístup k textu ve vyrovnávací paměti, který je orientovaný na proud.|
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsUserData>|Poskytuje přístup k obecné kolekci vlastností. Nejdůležitější vlastností je název nebo moniker vyrovnávací paměti. Vlastní náhodná data můžete do vyrovnávací paměti ukládat pomocí tohoto rozhraní tak, že vytvoříte identifikátor GUID a použijete ho jako klíč.|
|<xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPointContainer>|Podporuje body připojení pro události.|

## <a name="remarks"></a>Poznámky
 Objekt `VSTextBuffer` je obvykle nalezen `QueryInterface` voláním na `IVsTextBuffer` . Další informace najdete v tématu [vyrovnávací paměť textu](../vs-2015/extensibility/accessing-the-text-buffer-by-using-the-legacy-api.md?view=vs-2015).

## <a name="see-also"></a>Viz také:
- <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer>
- <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextView>
- [Úpravy obrázků](https://www.microsoft.com/download/details.aspx?id=55984)