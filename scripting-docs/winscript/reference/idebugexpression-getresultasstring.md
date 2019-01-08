---
title: IDebugExpression::GetResultAsString | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugExpression.GetResultAsString
apilocation:
- jscript.dll
helpviewer_keywords:
- IDebugExpression::GetResultAsString
ms.assetid: edadd2ad-9369-4878-bf87-cea15be9f363
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6cee33b5547e30f913407b02a3befd449dda6aeb
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54097354"
---
# <a name="idebugexpressiongetresultasstring"></a>IDebugExpression::GetResultAsString
Vrátí výsledek vyhodnocení výrazu jako řetězec a návratová hodnota operace.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT GetResultAsString(  
   HRESULT*  phrResult,  
   BSTR*     pbstrResult  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `phrResult`  
 [out] Návratová hodnota operace.  
  
 `pbstrResult`  
 [out] Výsledek vyhodnocení výrazu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
|`E_PENDING`|Operace je stále čekající na vyřízení.|  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda vrací výsledek vyhodnocení výrazu jako řetězec a operace `HRESULT`.  
  
 Tato metoda vrátí `S_OK` a `phrResult` vrátí `E_ABORT` Pokud `Abort` operaci zruší.  
  
## <a name="see-also"></a>Viz také  
 [IDebugExpression – rozhraní](../../winscript/reference/idebugexpression-interface.md)