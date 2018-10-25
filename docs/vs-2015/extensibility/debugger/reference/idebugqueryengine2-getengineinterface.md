---
title: IDebugQueryEngine2::GetEngineInterface | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugQueryEngine2::GetEngineInterface
helpviewer_keywords:
- IDebugQueryEngine2::GetEngineInterface
ms.assetid: ed84aa98-7ec7-48f3-97ae-821090bc3664
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 1d8470db2bcb8b4b1d734c7300ae4e3f5d120de1
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/23/2018
ms.locfileid: "49811877"
---
# <a name="idebugqueryengine2getengineinterface"></a>IDebugQueryEngine2::GetEngineInterface
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Získá rozhraním vlastního ladicího stroje (DE).  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT GetEngineInterface(   
   IUnknown** ppUnk  
);  
```  
  
```csharp  
int GetEngineInterface(   
   out object ppUnk  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ppUnk`  
 [out] Vrátí `IUnknown` objekt představuje ladicího stroje (DE) a který může být dotázán na platná rozhraní přidružené k Zavedenými (například [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md) nebo [IDebugEngineLaunch2](../../../extensibility/debugger/reference/idebugenginelaunch2.md)).  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Výsledný rozhraní by měl použít opatrně, protože volání prostřednictvím rozhraní načíst z této metody obchází zpracování správce ladění relace a může vést k SDM převedení do špatném stavu nebo generování chyb během ladění.  
  
## <a name="see-also"></a>Viz také  
 [IDebugQueryEngine2](../../../extensibility/debugger/reference/idebugqueryengine2.md)   
 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)   
 [IDebugEngineLaunch2](../../../extensibility/debugger/reference/idebugenginelaunch2.md)

