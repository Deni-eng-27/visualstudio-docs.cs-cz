---
title: IVariantChangeType::ChangeType | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IVariantChangeType.ChangeType
apilocation:
- scrobj.dll
helpviewer_keywords:
- IVariantChangeType::ChangeType
ms.assetid: 52374764-c42e-49af-a219-ee00c535a118
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0a02b8a3991ff6d20370cd4a2ea4cd87aa9a1226
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54086577"
---
# <a name="ivariantchangetypechangetype"></a>IVariantChangeType::ChangeType
Vezme hodnotu typu variant a vytvoří novou variantu pomocí zadaného typu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT ChangeType(  
   VARIANT*  pvarDst,  
   VARIANT*  pvarSrc,  
   LCID  lcid,  
   VARTYPE  vtNew  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pvarDst`  
 [out v] Hodnotu typu variant obsahující Hodnota reprezentovaná `pvarSrc`, ale v typu zadaném pomocí `vtNew`.  
  
 `pvarSrc`  
 [in] Varianty hodnota změny do nového typu.  
  
 `lcid`  
 [in] Kontext národního prostředí, který se má použít při převodu argumentů do nebo z řetězce.  
  
 `vtNew`  
 [in] Určuje typ `pvarDst` stát.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
 `pvarDst` a `pvarSrc` argumenty mohou být stejné, v takovém případě se přepíše původní hodnotu. Tato metoda předává `pvarDst` k `VariantClear` funkce a proto `pvarDst` by se měl inicializovat na platnou hodnotu.  
  
## <a name="see-also"></a>Viz také  
 [IVariantChangeType – rozhraní](../../winscript/reference/ivariantchangetype-interface.md)