---
title: IDebugBoundBreakpoint2::GetState | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugBoundBreakpoint2::GetState
helpviewer_keywords:
- GetState method
- IDebugBoundBreakpoint2::GetState method
ms.assetid: a40a8382-295e-4916-aae6-ffe3a9cd3f2d
caps.latest.revision: 12
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: b2bab406e84eee11dbfe73a70975fc69bd209930
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68156221"
---
# <a name="idebugboundbreakpoint2getstate"></a>IDebugBoundBreakpoint2::GetState
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Získá stav vázaná zarážka.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT GetState(   
   BP_STATE* pState  
);  
```  
  
```csharp  
int GetState(   
   out enum_BP_STATE pState  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pState`  
 [out] Vrátí hodnotu z [BP_STATE](../../../extensibility/debugger/reference/bp-state.md) výčet popisující stav zarážky.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak implementovat tuto metodu pro jednoduchý `CBoundBreakpoint` objekt, který zveřejňuje [IDebugBoundBreakpoint2](../../../extensibility/debugger/reference/idebugboundbreakpoint2.md) rozhraní.  
  
```  
HRESULT CBoundBreakpoint::GetState(BP_STATE* pState)    
{    
   HRESULT hr;    
  
   // Check for a valid pointer to pState and assign the local state variable.    
   if (pState)    
   {    
      *pState = m_state;    
      hr = S_OK;    
   }    
   else    
   {    
      hr = E_INVALIDARG;    
   }    
  
   return hr;    
}    
```  
  
## <a name="see-also"></a>Viz také  
 [IDebugBoundBreakpoint2](../../../extensibility/debugger/reference/idebugboundbreakpoint2.md)   
 [BP_STATE](../../../extensibility/debugger/reference/bp-state.md)
