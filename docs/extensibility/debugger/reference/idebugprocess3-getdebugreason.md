---
title: IDebugProcess3::GetDebugReason | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugProcess3::GetDebugReason
helpviewer_keywords:
- IDebugProcess3::GetDebugReason
ms.assetid: f23fbabc-8b18-4278-bebf-4cdc7091513c
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 733818736c6a6eaf8428a50aa9a1cf153d578a2e
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53914063"
---
# <a name="idebugprocess3getdebugreason"></a>IDebugProcess3::GetDebugReason
Tato metoda vrací z důvodu, že proces byl spuštěn pro ladění.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetDebugReason(  
   DEBUG_REASON* pReason  
);  
```  
  
```csharp  
int GetDebugReason(  
   out enum_DEBUG_REASON pReason  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pReason`  
 [out] Vrátí hodnotu z [DEBUG_REASON](../../../extensibility/debugger/reference/debug-reason.md) výčtu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IDebugProcess3](../../../extensibility/debugger/reference/idebugprocess3.md)   
 [DEBUG_REASON](../../../extensibility/debugger/reference/debug-reason.md)