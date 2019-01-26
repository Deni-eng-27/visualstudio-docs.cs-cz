---
title: IEEVisualizerService | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IEEVisualizerService
helpviewer_keywords:
- IEEVisualizerService interface
ms.assetid: 3bdb124b-c582-47ba-b465-13c6a1cdb702
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 30cc53b09d82ac762b48b5682b3c564695a984a2
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55022336"
---
# <a name="ieevisualizerservice"></a>IEEVisualizerService
> [!IMPORTANT]
>  V sadě Visual Studio 2015 je zastaralý tímto způsobem implementace vyhodnocovače výrazů. Informace o implementace vyhodnocovače výrazů modulu CLR najdete v tématu [vyhodnocovače výrazů modulu CLR](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) a [spravované ukázka Chyba při vyhodnocování výrazu](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 Toto rozhraní implementuje klíčové metody, které poskytují funkce, které [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md) a [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md) rozhraní.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IEEVisualizerService : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Visual Studio implementuje toto rozhraní umožňuje vyhodnocovače výrazů (EE) pro podporu vizualizérů typů.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Volání EE [CreateVisualizerService](../../../extensibility/debugger/reference/ieevisualizerserviceprovider-createvisualizerservice.md) získat toto rozhraní jako součást své podpory pro vizualizérů typů.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetCustomViewerCount](../../../extensibility/debugger/reference/ieevisualizerservice-getcustomviewercount.md)|Získá počet vlastních prohlížečů, o kterých ví této služby.|  
|[GetCustomViewerList](../../../extensibility/debugger/reference/ieevisualizerservice-getcustomviewerlist.md)|Načte seznam vlastních prohlížečů.|  
|[GetPropertyProxy](../../../extensibility/debugger/reference/ieevisualizerservice-getpropertyproxy.md)|Vrátí objekt proxy pro vlastnost.|  
|[GetValueDisplayStringCount](../../../extensibility/debugger/reference/ieevisualizerservice-getvaluedisplaystringcount.md)|Získá počet řetězců hodnota má být zobrazen pro zadanou vlastnost nebo pole.|  
  
## <a name="remarks"></a>Poznámky  
 Využívá integrovaného vývojového prostředí [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md) rozhraní určí, jestli jsou všechny vlastních prohlížečů nebo zadejte pro vlastnost vizualizéry. Vytvořením služby visualizéru (s [CreateVisualizerService](../../../extensibility/debugger/reference/ieevisualizerserviceprovider-createvisualizerservice.md)), EE můžete zadat funkci, která `IDebugProperty3` a [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md) (který podporuje zobrazení a změna Hodnota vlastnosti) rozhraní a podporovat tak vizualizérů typů.  
  
 Pokud má EE vlastních prohlížečů, která implementuje, můžete připojit EE `CLSID`s těchto vlastních prohlížečů na konec seznamu vrácených [GetCustomViewerList](../../../extensibility/debugger/reference/ieevisualizerservice-getcustomviewerlist.md). To umožňuje EE pro podporu vizualizérů typů a vlastní vlastních prohlížečů. Právě Ujistěte se, že [GetCustomViewerCount](../../../extensibility/debugger/reference/idebugproperty3-getcustomviewercount.md) odráží součet všech vlastních prohlížečů.  
  
 Zobrazit [vizualizér typů a vlastní prohlížeč](../../../extensibility/debugger/type-visualizer-and-custom-viewer.md) diskuzi o rozdíl mezi vizualizérů a prohlížeče.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: ee.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Rozhraní pro vyhodnocení výrazu](../../../extensibility/debugger/reference/expression-evaluation-interfaces.md)   
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md)   
 [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md)   
 [CreateVisualizerService](../../../extensibility/debugger/reference/ieevisualizerserviceprovider-createvisualizerservice.md)   
 [Vizualizér typů a vlastní prohlížeč](../../../extensibility/debugger/type-visualizer-and-custom-viewer.md)