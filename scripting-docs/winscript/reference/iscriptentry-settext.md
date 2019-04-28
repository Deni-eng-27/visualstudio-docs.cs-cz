---
title: IScriptEntry::SetText | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IScriptEntry.SetText
apilocation:
- scrobj.dll
helpviewer_keywords:
- ISetEntry::SetText
ms.assetid: 4605481b-7707-43d1-ab78-a9207d0cf6fe
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 17e716a7ad52cc5aeca18d02122edb9c457b14e4
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62787629"
---
# <a name="iscriptentrysettext"></a>IScriptEntry::SetText
Nastaví text, který odpovídá `IScriptEntry` bloku skriptu nebo zdrojový kód, který je součástí `IScriptScriptlet` obslužné rutiny události.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT SetText(  
   LPCOLESTR          psz  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `psz`  
 [in] Text `IScriptEntry` bloku skriptu nebo zdrojový kód `IScriptScriptlet` obslužné rutiny události.  
  
## <a name="return-value"></a>Návratová hodnota  
 `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
  
## <a name="see-also"></a>Viz také  
 [IScriptEntry – rozhraní](../../winscript/reference/iscriptentry-interface.md)