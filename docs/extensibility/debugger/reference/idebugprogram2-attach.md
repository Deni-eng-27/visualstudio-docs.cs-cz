---
title: IDebugProgram2::Attach | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugProgram2::Attach
helpviewer_keywords: IDebugProgram2::Attach
ms.assetid: de069fbf-a565-4905-b102-f5658c55aacd
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 60127ceb0cb177bd8532d2e20ebc1afebeb90937
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idebugprogram2attach"></a>IDebugProgram2::Attach
Připojí se k programu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT Attach(   
   IDebugEventCallback2* pCallback  
);  
```  
  
```csharp  
int Attach(   
   IDebugEventCallback2 pCallback  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pCallback`  
 [v] [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) objekt, který chcete použít pro oznámení o události ladění.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby. V následující tabulce jsou uvedeny některé možné chybové kódy.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`E_ATTACH_DEBUGGER_ALREADY_ATTACHED`|Zadaný program je již připojen k ladicího programu.|  
|`E_ATTACH_DEBUGGEE_PROCESS_SECURITY_VIOLATION`|Během procesu připojení došlo k narušení zabezpečení.|  
|`E_ATTACH_CANNOT_ATTACH_TO_DESKTOP`|Desktopovému programu nelze připojit k ladicího programu.|  
  
## <a name="remarks"></a>Poznámky  
 Modul ladění (DE) nikdy volá tuto metodu za účelem připojení k programu. Pokud je DE spustí v programu adresního prostoru, [OnAttach](../../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md) metoda je volána. Pokud se spustí DE ve Správci ladicí relace (SDM) adresní prostor, [Attach](../../../extensibility/debugger/reference/idebugengine2-attach.md) metoda je volána.  
  
## <a name="see-also"></a>Viz také  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)   
 [OnAttach](../../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md)   
 [Připojení](../../../extensibility/debugger/reference/idebugengine2-attach.md)