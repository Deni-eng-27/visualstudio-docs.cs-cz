---
title: Vstextbuffer – objekt | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- VSTextBuffer
helpviewer_keywords:
- VSTextBuffer object, reference
- views [Visual Studio SDK], VSTextBuffer object
ms.assetid: c5f94b45-7249-4e1f-a53d-1d2a1c61e0ef
caps.latest.revision: 10
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 950f9c50ccaf137b21d775ceaf1bff196b1b8ac7
ms.sourcegitcommit: 447f2174bdecdd471d8a8e11c19554977db620a0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/28/2019
ms.locfileid: "55089299"
---
# <a name="vstextbuffer-object"></a>VSTextBuffer – objekt
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Objekt vyrovnávací paměti textu představuje datový proud text v kódu Unicode, který je obvykle přidružen soubor. A <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer> objekt lze použít mimo kontext základní editor, třeba v případě průvodce.  
  
 V následující tabulce jsou uvedeny rozhraní `VSTextBuffer`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IOleCommandTarget](/windows/desktop/api/docobj/nn-docobj-iolecommandtarget)|Standardní rozhraní OLE. Používá se hlavně pro zpracování ve vyrovnávací paměti zpět/znovu.|  
|[IPersistFile](/windows/desktop/api/objidl/nn-objidl-ipersistfile)|Standardní rozhraní OLE.|  
|[IPersistStream](/windows/desktop/api/objidl/nn-objidl-ipersiststream)|Standardní rozhraní OLE.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsCompoundAction>|Umožňuje vytvořit sloučeniny akce (to znamená, akce, které jsou seskupeny do jednoho zpět/znovu jednotka).|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData>|Povolí trvalost dat dokumentu spravuje vyrovnávací paměti textu.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer>|Poskytuje základní služby; používá mnoho klientů.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextFind>|Použitá k vyhledání vyrovnávací paměti.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines>|Umožňuje číst a zapisovat možnosti použití dvojrozměrné souřadnice. Dědí z `IVsTextBuffer`.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextStream>|Umožňuje číst a zapisovat možnosti pomocí souřadnic jednorozměrné. Dědí z `IVsTextBuffer`.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextScanner>|Poskytuje možnost rychlého, orientovaný na stream, sekvenční přístup k textu ve vyrovnávací paměti.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsUserData>|Poskytuje přístup k obecnou kolekci vlastností. Nejdůležitější vlastnost je název nebo moniker vyrovnávací paměti. Náhodná data můžete ukládat do vyrovnávací paměti s tímto rozhraním vytvořením identifikátor GUID a jeho použití jako klíč.|  
|<xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPointContainer>|Podporuje spojovací body události.|  
  
## <a name="remarks"></a>Poznámky  
 `VSTextBuffer` Je obvykle zjištěných aplikací `QueryInterface` volat `IVsTextBuffer`. Další informace najdete v tématu [textovou vyrovnávací paměť](../extensibility/accessing-the-text-buffer-by-using-the-legacy-api.md).  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextView>   
 [Úpravy obrázků](http://msdn.microsoft.com/f08872bd-fd9c-4e36-8cf2-a2a2622ef986)
