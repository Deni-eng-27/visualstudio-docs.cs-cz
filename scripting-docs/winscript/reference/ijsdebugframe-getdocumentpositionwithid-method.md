---
title: Ijsdebugframe::getdocumentpositionwithid – metoda | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IJsDebugFrame.GetDocumentPositionWithId
apilocation:
- jscript9diag.dll
ms.assetid: 48f8eb26-8ae4-4d5c-bd94-796023b03bcb
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4c37f31ca6b75ca826dbdab93847a1e70ff054c1
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54090009"
---
# <a name="ijsdebugframegetdocumentpositionwithid-method"></a>IJsDebugFrame::GetDocumentPositionWithId – metoda
Vrací aktuální pozici tohoto rámce zásobníku v rámci dokumentu uživatelské úrovni.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT GetDocumentPositionWithId(  
   UINT64 *pDocumentId,  
   DWORD *pCharacterOffset,  
   DWORD *pStatementCharCount  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pDocumentId`  
 [out] Jedinečné ID pro zdrojový dokument (ukazatel na IDebugDocumentText).  
  
 `pCharacterOffset`  
 [out] Odsazení znaku od nuly od začátku skriptu.  
  
 `pStatementCharCount`  
 [out] Délka aktuálního příkazu, který začíná * pCharacterOffset, ve znacích.  
  
## <a name="return-value"></a>Návratová hodnota  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** jscript9diag.h  
  
## <a name="see-also"></a>Viz také  
 [IJsDebugFrame – rozhraní](../../winscript/reference/ijsdebugframe-interface.md)