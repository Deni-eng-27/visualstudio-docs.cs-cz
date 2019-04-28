---
title: IActiveScript::GetScriptSite | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScript.GetScriptSite
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScript_GetScriptSite
ms.assetid: 83a2a89d-93d0-4cbd-9244-91a730cb406b
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b57c4282b7ec77eb4af2ffa983479ae77388e1c9
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62935768"
---
# <a name="iactivescriptgetscriptsite"></a>IActiveScript::GetScriptSite
Načte objekt lokality přidružený modul skriptu Windows.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT GetScriptSite(  
    REFIID iid,           // interface identifier  
    void **ppvSiteObject  // address of host site interface  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `iid`  
 [in] Identifikátor požadované rozhraní.  
  
 `ppvSiteObject`  
 [out] Adresa umístění, která přijímá ukazatel rozhraní na objekt sítě hostiteli.  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrátí jednu z následujících hodnot:  
  
|Návratová hodnota|Význam|  
|------------------|-------------|  
|`S_OK`|Úspěch.|  
|`E_INVALIDARG`|Argument byl neplatný.|  
|`E_NOINTERFACE`|Zadané rozhraní není podporováno.|  
|`E_POINTER`|Byl zadán neplatný ukazatel.|  
|`S_FALSE`|Žádná lokalita byla nastavena; `ppvSiteObject` parametr je nastaven na `NULL`.|  
  
## <a name="see-also"></a>Viz také  
 [IActiveScript](../../winscript/reference/iactivescript.md)