---
title: Objekt VSTextBuffer | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VSTextBuffer
helpviewer_keywords:
- VSTextBuffer object, reference
- views [Visual Studio SDK], VSTextBuffer object
ms.assetid: c5f94b45-7249-4e1f-a53d-1d2a1c61e0ef
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 643bd434e058a24cc17936d9ab2f333489b8aa5e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="vstextbuffer-object"></a>Objekt VSTextBuffer
Objekt textové vyrovnávací paměti představuje proud text v kódu Unicode, které je obecně přidružené k souboru. A <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer> objekt lze použít mimo kontext jádra editoru, jako v případě průvodce.  
  
 V následující tabulce jsou uvedeny rozhraní `VSTextBuffer`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IOleCommandTarget](http://msdn.microsoft.com/library/windows/desktop/ms683797)|Standardní rozhraní OLE. Používá se především pro vrácení zpět/opakování zpracování ve vyrovnávací paměti.|  
|[IPersistFile](http://msdn.microsoft.com/library/windows/desktop/ms687223)|Standardní rozhraní OLE.|  
|[Rozhraní IPersistStream](http://msdn.microsoft.com/library/windows/desktop/ms690091)|Standardní rozhraní OLE.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsCompoundAction>|Umožňuje vytvoření sloučeniny akcí (to znamená, akce, které jsou seskupené v jednotce jeden zpět/opakování).|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData>|Povolí zachování dokumentu data spravovaná přes textová vyrovnávací paměť.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer>|Poskytuje základní služby; používá mnoho klientů.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextFind>|Slouží k hledání vyrovnávací paměti.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines>|Poskytuje pro čtení a zápis možnosti pomocí dvourozměrná souřadnic. Dědí z `IVsTextBuffer`.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextStream>|Poskytuje pro čtení a zápis možnosti pomocí jednorozměrné souřadnic. Dědí z `IVsTextBuffer`.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextScanner>|Poskytuje možnost rychlého, orientované na datový proud, sekvenční přístup k textu ve vyrovnávací paměti.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsUserData>|Poskytuje přístup k obecnou kolekci vlastností. Nejdůležitější vlastnost je název, nebo Přezdívka vyrovnávací paměti. Vlastní náhodná data můžete uložit ve vyrovnávací paměti s tímto rozhraním vytvořením identifikátor GUID a jeho použití jako klíč.|  
|<xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPointContainer>|Body připojení podporuje pro události.|  
  
## <a name="remarks"></a>Poznámky  
 `VSTextBuffer` Obvykle zjistí, že `QueryInterface` volání na `IVsTextBuffer`. Další informace najdete v tématu [textovou vyrovnávací paměť](../extensibility/accessing-the-text-buffer-by-using-the-legacy-api.md).  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextView>   
 [Úprava obrázků](http://msdn.microsoft.com/en-us/f08872bd-fd9c-4e36-8cf2-a2a2622ef986)