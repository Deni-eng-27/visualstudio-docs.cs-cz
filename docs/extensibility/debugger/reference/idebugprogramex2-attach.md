---
title: IDebugProgramEx2::Attach | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugProgramEx2::Attach
helpviewer_keywords:
- IDebugProgramEx2::Attach
ms.assetid: 33b22b2f-431e-4205-9441-d28a9c928c97
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: f885bd3cdd09caa145451e922ad154b60fdb1ff4
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53900584"
---
# <a name="idebugprogramex2attach"></a>IDebugProgramEx2::Attach
Relaci připojení k programu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT Attach(   
   IDebugEventCallback2* pCallback,  
   DWORD                 dwReason,  
   IDebugSession2*       pSession  
);  
```  
  
```  
[C#]  
int Attach(   
   IDebugEventCallback2 pCallback,  
   uint                 dwReason,  
   IDebugSession2       pSession  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pCallback`  
 [in] [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) objekt, který reprezentuje funkce zpětného volání, která odesílá události do připojeného ladicího stroje.  
  
 `dwReason`  
 [in] Hodnota z [ATTACH_REASON](../../../extensibility/debugger/reference/attach-reason.md) výčet, který je popsaný i důvod pro operace připojení.  
  
 `pSession`  
 [in] Hodnota, která jednoznačně identifikuje relace, která se připojuje k programu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby. Tato metoda by měla vrátit `E_ATTACH_DEBUGGER_ALREADY_ATTACHED` Pokud program je již připojen.  
  
## <a name="remarks"></a>Poznámky  
 Port, který obsahuje program můžete použít hodnotu v `pSession` k určení, které relace se pokouší připojit k programu. Například pokud port umožňuje pouze jednu ladicí relaci se připojit k procesu najednou, port, který můžete určit, pokud stejné relace je již připojena k jiné programy v procesu.  
  
> [!NOTE]
>  Předané rozhraní `pSession` je považován za pouze do souboru cookie, hodnotu, která jednoznačně identifikuje správce ladění relace připojení k tomuto programu; žádný z metod na zadané rozhraní není funkční.  
  
## <a name="see-also"></a>Viz také  
 [IDebugProgramEx2](../../../extensibility/debugger/reference/idebugprogramex2.md)