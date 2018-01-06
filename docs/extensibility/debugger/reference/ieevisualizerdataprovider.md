---
title: IEEVisualizerDataProvider | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IEEVisualizerDataProvider
helpviewer_keywords: IEEVisualizerDataProvider interface
ms.assetid: 5fdfe6e3-b94e-4edb-acc5-41d8773d8ca5
caps.latest.revision: "15"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: edf2cfe689caa58e1c0402a91fa31237cb2c7215
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="ieevisualizerdataprovider"></a>IEEVisualizerDataProvider
> [!IMPORTANT]
>  V sadě Visual Studio 2015 se již nepoužívá tímto způsobem implementace vyhodnocovače výrazů. Informace o implementaci vyhodnocovače výrazů CLR, najdete v tématu [vyhodnocovače výrazů CLR](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) a [spravované ukázka vyhodnocování výrazu](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 Toto rozhraní umožňuje změnit hodnoty objektu prostřednictvím vizualizéru typu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IEEVisualizerDataProvider : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Vyhodnocení výrazu implementuje toto rozhraní pro podporu změny dat na objekt vlastnosti prostřednictvím vizualizéru typu.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Toto rozhraní je použité při vytváření [IEEVisualizerService](../../../extensibility/debugger/reference/ieevisualizerservice.md) objektu prostřednictvím volání [CreateVisualizerService](../../../extensibility/debugger/reference/ieevisualizerserviceprovider-createvisualizerservice.md). V tématu [Visualizing a zobrazení Data](../../../extensibility/debugger/visualizing-and-viewing-data.md) další podrobnosti.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
  
|Metoda|Popis|  
|------------|-----------------|  
|[CanSetObjectForVisualizer](../../../extensibility/debugger/reference/ieevisualizerdataprovider-cansetobjectforvisualizer.md)|Určuje, zda je možné k aktualizaci objektu (a následně, jeho hodnota), je tato vizualizér představující.|  
|[GetNewObjectForVisualizer](../../../extensibility/debugger/reference/ieevisualizerdataprovider-getnewobjectforvisualizer.md)|Vynutí se tak opakované vyhodnocení objektu pro tuto vizualizér.|  
|[GetObjectForVisualizer](../../../extensibility/debugger/reference/ieevisualizerdataprovider-getobjectforvisualizer.md)|Získá existujícího objektu pro tuto vizualizér (bez vyhodnocení se provádí).|  
|[SetObjectForVisualizer](../../../extensibility/debugger/reference/ieevisualizerdataprovider-setobjectforvisualizer.md)|Aktualizuje objekt pro tento vizualizér, a tím změnit hodnotu, kterou vizualizér uvede.|  
  
## <a name="remarks"></a>Poznámky  
 Službu vizualizér (reprezentovaná [IEEVisualizerService](../../../extensibility/debugger/reference/ieevisualizerservice.md) rozhraní a vrácený [CreateVisualizerService](../../../extensibility/debugger/reference/ieevisualizerserviceprovider-createvisualizerservice.md)) udržuje odkaz na objekt implementace `IEEVisualizerDataProvider` rozhraní . V důsledku toho `IEEVisualizerDataProvider` rozhraní by neměl být implementováno na stejný objekt, který implementuje [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) Pokud udržuje odkaz na tento objekt `IEEVisualizerService` objektu: výsledků cyklický odkaz a zablokování nastane, když jsou zničení objektů. Doporučený přístup je implementovat `IEEVisualizerDataProvider` na samostatný objekt, ke kterému `IDebugProperty2` objektu delegáti bez volání `IUnknown::AddRef` na něm.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: ee.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Rozhraní vyhodnocení výrazu](../../../extensibility/debugger/reference/expression-evaluation-interfaces.md)   
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [IEEVisualizerService](../../../extensibility/debugger/reference/ieevisualizerservice.md)   
 [IEEVisualizerServiceProvider](../../../extensibility/debugger/reference/ieevisualizerserviceprovider.md)   
 [Vizualizace a zobrazení dat](../../../extensibility/debugger/visualizing-and-viewing-data.md)