---
title: IDebugAddress2::GetProcessID | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugAddress2::GetProcessID
helpviewer_keywords: IDebugAddress2::GetProcessID method
ms.assetid: 2c18889d-074a-4b95-87b4-bf1a067f44ed
caps.latest.revision: "6"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 35ed788f5ac49b92b8702d433aa46df7571267d2
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idebugaddress2getprocessid"></a>IDebugAddress2::GetProcessID
Načte ID procesu, který vlastní objekt reprezentovaný rozhraním to [IDebugAddress2](../../../extensibility/debugger/reference/idebugaddress2.md) rozhraní.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetProcessID (  
   DWORD* pProcID  
);  
```  
  
```csharp  
int GetProcessID (  
   out uint pProcID  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pProcID`  
 [out] ID procesu.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí S_OK; jinak vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IDebugAddress2](../../../extensibility/debugger/reference/idebugaddress2.md)