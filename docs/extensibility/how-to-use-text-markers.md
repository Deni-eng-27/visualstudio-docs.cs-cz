---
title: 'Postupy: použití značek Text | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - using text markers
ms.assetid: 76eed51c-eecb-4579-823e-13df2f0526b9
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 1f5267295875976ac5370d97f186307637a49b6d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-use-text-markers"></a>Postupy: použití značek textu
Text značky lze použít pro upravit <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer> objektu.  
  
## <a name="procedures"></a>Procedury  
  
#### <a name="to-apply-text-markers"></a>Chcete-li použít text značek  
  
1.  Získat instanci <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextManager> třídy.  
  
    > [!NOTE]
    >  Značky standardního textového editoru základní automaticky platí pro všechny dokument, který je úpravy a neměl by být potřeba použít standardní text značek explicitně.  
  
2.  Získání ID typu značky značky zajímá voláním <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextManager.GetRegisteredMarkerTypeID%2A> metoda s `GUID` text značky chcete pracovat.  
  
    > [!NOTE]
    >  Nepoužívejte `GUID` VSPackage nebo služba, která poskytuje text značky.  
  
3.  Použití ID typu značky získá voláním <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextManager.GetRegisteredMarkerTypeID%2A> metoda jako parametr pro volání <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines.CreateLineMarker%2A> metoda nebo <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextStream.CreateStreamMarker%2A> metodu chcete použít značku text pro příslušnou oblast textu.  
  
#### <a name="to-add-features-to-text-markers"></a>Pro přidání funkcí do textu značek  
  
1.  To může být žádoucí pro přidání dalších funkcí do textu značku, jako je například popisy, speciální kontextové nabídky nebo obslužná rutina pro zvláštní okolnosti. Postupujte následovně:  
  
2.  Vytvoření implementace objektu <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient> rozhraní.  
  
3.  V případě potřeby další funkce implementovat <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClientEx>a <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClientAdvanced> rozhraní pro stejný objekt, který implementuje <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient> rozhraní.  
  
4.  Předat <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient> rozhraní, které vytvoříte, k volání <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines.CreateLineMarker%2A> metoda nebo <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextStream.CreateStreamMarker%2A> metoda používá k aplikování značky textu pro danou oblast textu.  
  
5.  Při přidávání kontextové nabídky podpory v oblasti textového značky je nutné vytvořit v nabídce.  
  
     Další informace o tom, jak vytvořit nabídky naleznete v kontextu [kontextové nabídky](../extensibility/context-menus.md).  
  
6.  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Prostředí volá metody, zadaný rozhraní, jako <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient.GetTipText%2A> metody nebo <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient.ExecMarkerCommand%2A> metoda podle potřeby.  
  
## <a name="see-also"></a>Viz také  
 [Text značky pomocí starší verze rozhraní API](../extensibility/using-text-markers-with-the-legacy-api.md)   
 [Postupy: Přidání značek standardního textu](../extensibility/how-to-add-standard-text-markers.md)   
 [Postupy: vytvoření vlastní Text značek](../extensibility/how-to-create-custom-text-markers.md)   
 [Postupy: implementace chyba značky](../extensibility/how-to-implement-error-markers.md)