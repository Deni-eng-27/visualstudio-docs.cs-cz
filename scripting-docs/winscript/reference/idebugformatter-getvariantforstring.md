---
title: IDebugFormatter::GetVariantForString | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugFormatter.GetVariantForString
apilocation:
- jscript.dll
helpviewer_keywords:
- IDebugFormatter::GetVariantForString
ms.assetid: 2993431d-0ee2-4d8d-b62c-0a810a8bc391
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ea6cd1f77481282700de492e2857046044a04e2a
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62979286"
---
# <a name="idebugformattergetvariantforstring"></a>IDebugFormatter::GetVariantForString
Vrátí hodnotu typu VARIANT obsahující daný řetězec.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT GetVariantForString(  
   LPCOLESTR  pwstrValue,  
   VARIANT*   pvar  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pwstrValue`  
 [in] Řetězec k uložení v hodnotu typu VARIANT.  
  
 `pvar`  
 [out] Hodnota typu VARIANT obsahující `pwstrValue`.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Value|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda vrátí hodnotu typu VARIANT obsahující daný řetězec.  
  
## <a name="see-also"></a>Viz také  
 [IDebugFormatter – rozhraní](../../winscript/reference/idebugformatter-interface.md)