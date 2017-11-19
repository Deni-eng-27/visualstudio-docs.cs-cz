---
title: "Idiastackframe::get_rawlvarinstancevalue – | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaStackFrame::get_rawLVarInstanceValue method
ms.assetid: ce526259-85a6-475b-9274-0b3a21d95db2
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5559ad617afbb2ae4a65ecbf399f7f79d93ae1c7
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idiastackframegetrawlvarinstancevalue"></a>IDiaStackFrame::get_rawLVarInstanceValue
Tato metoda načte hodnotu zadaného místní proměnné nezpracovaná bajtů.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT get_rawLVarInstanceValue(  
   IDiaLVarInstance* pInstance,  
   DWORD             cbDataMax,  
   DWORD*            pcbData,  
   BYTE*             pbData  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pInstance`  
 [v] `IDiaLVarInstance` Objekt reprezentující instanci k získání hodnoty pro místní proměnné.  
  
 `cbDataMax`  
 [v] Maximální počet bajtů ve vyrovnávací paměti na kterou odkazuje `pbData`. To může být maximálně 8 bajtů (`sizeof(ULONGLONG)`).  
  
 `pcbData`  
 [out] Vrátí skutečný počet bajtů, které jsou uložené ve vyrovnávací paměti.  
  
 `pbData`  
 [out] Vyrovnávací paměť pro vyplnění data. Nesmí to být `NULL`.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [Idiastackframe –](../../debugger/debug-interface-access/idiastackframe.md)