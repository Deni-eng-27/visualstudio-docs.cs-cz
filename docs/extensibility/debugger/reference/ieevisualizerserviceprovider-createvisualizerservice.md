---
title: IEEVisualizerServiceProvider::CreateVisualizerService | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IEEVisualizerServiceProvider::CreateVisualizerService
helpviewer_keywords:
- IEEVisualizerServiceProvider::CreateVisualizerService method
ms.assetid: f366f7c9-358d-46c8-993f-32ff86539833
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: b9c34f5b11aed9ed51ca10f662ea161d792e54b6
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="ieevisualizerserviceprovidercreatevisualizerservice"></a>IEEVisualizerServiceProvider::CreateVisualizerService
Tato metoda vytvoří vizualizér služby.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT CreateVisualizerService(  
   IDebugBinder*              binder,  
   IDebugSymbolProvider*      pSymProv,  
   IDebugAddress*             pAddress,  
   IEEVisualizerDataProvider* dataProvider,  
   IEEVisualizerService**     ppService  
);  
```  
  
```csharp  
int CreateVisualizerService(  
   IDebugBinder binder,  
   IDebugSymbolProvider      pSymProv,  
   IDebugAddress             pAddress,  
   IEEVisualizerDataProvider dataProvider,  
   out IEEVisualizerService  ppService  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `binder`  
 [v] [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md) byl předán objekt [EvaluateSync](../../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md).  
  
 `pSymProv`  
 [v] [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md) byl předán objekt `IDebugParsedExpression::EvaluateSync`.  
  
 `pAddress`  
 [v] [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) byl předán objekt `IDebugParsedExression::EvaluateSync`.  
  
 `dataProvider`  
 [v] Implementaci objektu [IEEVisualizerDataProvider](../../../extensibility/debugger/reference/ieevisualizerdataprovider.md) rozhraní (poskytl vyhodnocovací filtr výrazů).  
  
 `ppService`  
 [out] Vytvoření služby.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 `binder`, `pSymProv`, A `pAddress` parametry byly předány do `IDebugParsedExpression::EvaluateSync` metoda. `CreateVisualizerService`je možné volat jenom z `IDebugParsedExpression::EvaluateSync` v rámci podpory vyhodnocení výrazu pro typ vizualizérech.  
  
## <a name="see-also"></a>Viz také  
 [IEEVisualizerServiceProvider](../../../extensibility/debugger/reference/ieevisualizerserviceprovider.md)   
 [EvaluateSync](../../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md)   
 [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md)   
 [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md)   
 [IEEVisualizerDataProvider](../../../extensibility/debugger/reference/ieevisualizerdataprovider.md)