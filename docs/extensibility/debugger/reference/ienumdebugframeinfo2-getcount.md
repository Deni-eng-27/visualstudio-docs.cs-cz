---
title: IEnumDebugFrameInfo2::GetCount | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IEnumDebugFrameInfo2::GetCount
helpviewer_keywords: IEnumDebugFrameInfo2::GetCount
ms.assetid: d02a08e3-f34f-461e-8195-5157e154c481
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 895666bed2442c7b45a678525778878f7674f5d9
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="ienumdebugframeinfo2getcount"></a>IEnumDebugFrameInfo2::GetCount
Vrátí počet elementů ve výčtu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetCount(  
   ULONG* pcelt  
);  
```  
  
```csharp  
int GetCount(  
   out uint pcelt  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pcelt`  
 [out] Vrátí počet elementů ve výčtu.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda není součástí obvyklé – výčet rozhraní modelu COM, která určuje pouze `Next`, `Clone`, `Skip`, a `Reset` metody musí být implementována.  
  
## <a name="see-also"></a>Viz také  
 [IEnumDebugFrameInfo2](../../../extensibility/debugger/reference/ienumdebugframeinfo2.md)