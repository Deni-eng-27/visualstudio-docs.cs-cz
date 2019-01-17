---
title: IDebugApplicationThread110::AsynchronousCallIntoThread | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 06b3031a-4aec-4a47-afaa-04642a4c4870
caps.latest.revision: 2
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2392d34a4971389b293e44a6223c2159d6d6a9cb
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/16/2019
ms.locfileid: "54345848"
---
# <a name="idebugapplicationthread110asynchronouscallintothread"></a>IDebugApplicationThread110::AsynchronousCallIntoThread
Provede asynchronní volání v hlavním vlákně.  
  
> [!IMPORTANT]
>  [Idebugapplicationthread110 – rozhraní](../../winscript/reference/idebugapplicationthread110-interface.md) je implementováno komponentou Pdm verze 11.0 nebo novější. Nachází se v souboru activdbg100.h.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT AsynchronousCallInMainThread([in] IDebugThreadCall* pptc, [in] DWORD_PTR dwParam1, [in] DWORD_PTR dwParam2, [in] DWORD_PTR dwParam3);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pptc`  
 [Idebugthreadcall – rozhraní](../../winscript/reference/idebugthreadcall-interface.md) objekt volat.  
  
 `dwParam1`  
 První parametr volání.  
  
 `dwParam1`  
 První parametr volání.  
  
 `dwParam2`  
 Druhý parametr volání.  
  
 `dwParam3`  
 Třetí parametr volání.  
  
## <a name="see-also"></a>Viz také  
 [IDebugApplication110 – rozhraní](../../winscript/reference/idebugapplication110-interface.md)