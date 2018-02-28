---
title: IDebugProgram2::Continue | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugProgram2::Continue
helpviewer_keywords:
- IDebugProgram2::Continue
ms.assetid: e5a6e02a-d21b-4a03-a034-e8de1f71ce2e
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 5c90c456c4825ea9da054f7e78621493cc90a648
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugprogram2continue"></a>IDebugProgram2::Continue
Dál spuštěním tohoto programu z zastaveném stavu. Uchování jakékoli předchozí stav spuštění (například krok), a program se spustí provádění znovu.  
  
> [!NOTE]
>  Tato metoda je zastaralá. Použití [pokračovat](../../../extensibility/debugger/reference/idebugprocess3-continue.md) metoda místo.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT Continue(   
   IDebugThread2* pThread  
);  
```  
  
```csharp  
int Continue(   
   IDebugThread2 pThread  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pThread`  
 [v] [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md) objekt, který reprezentuje vlákno.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda je volána na tento program bez ohledu na to, kolik programy se právě ladí nebo program, který vygeneruje událost zastavit. Implementace musí zachovat předchozí stav spuštění (například krok) a pokračovat v provádění, jako by měl nikdy zastaven před dokončením vykonávání předchozí. To znamená, pokud vlákna v tento program dělal operaci krok převzetí a byla zastavena, protože některé jiný program zastaví, a pak se tato metoda volána, program musí původní krok přes operaci dokončit.  
  
> [!WARNING]
>  Neodesílat zastavení události nebo okamžitou (synchronní) události [událostí](../../../extensibility/debugger/reference/idebugeventcallback2-event.md) při zpracování volání; v opačném případě ladicí program může přestat reagovat.  
  
## <a name="see-also"></a>Viz také  
 [IDebugEngineProgram2](../../../extensibility/debugger/reference/idebugengineprogram2.md)   
 [Události](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)