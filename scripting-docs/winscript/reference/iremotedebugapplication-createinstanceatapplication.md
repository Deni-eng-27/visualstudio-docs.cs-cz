---
title: IRemoteDebugApplication::CreateInstanceAtApplication | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IRemoteDebugApplication.CreateInstanceAtApplication
apilocation:
- pdm.dll
helpviewer_keywords:
- IRemoteDebugApplication::CreateInstanceAtApplication
ms.assetid: d669ec80-2182-400d-87cc-7c1753315e5c
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6e17c5abcb21bfaad6de948c3676d29232da66cf
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62944318"
---
# <a name="iremotedebugapplicationcreateinstanceatapplication"></a>IRemoteDebugApplication::CreateInstanceAtApplication
Povolí vytváření objektů v procesu aplikace pomocí kódu, který je mimo proces k aplikaci.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT CreateInstanceAtApplication(  
   REFCLSID    rclsid,  
   IUnknown*   pUnkOuter,  
   DWORD       dwClsContext,  
   REFIID      riid,  
   IUnknown**  ppvObject  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `rclsid`  
 [in] Identifikátor (CLSID) objekt k vytvoření třídy.  
  
 `pUnkOuter`  
 [in] Pokud `NULL`, není objekt vytváří jako součást agregace. V opačném případě `pUnkOuter` je ukazatel na agregovaný objekt `IUnknown` rozhraní (řízení `IUnknown`).  
  
 `dwClsContext`  
 [in] Kontext spuštění spustitelného kódu. Hodnoty pocházejí z výčtu `CLSCTX`.  
  
 `riid`  
 [in] Identifikátor rozhraní používaný ke komunikaci s objektem.  
  
 `ppvObject`  
 [out] Adresa proměnné ukazatele, která přijímá ukazatel rozhraní požadované `riid`. Po návratu úspěšné *`ppvObject` obsahuje ukazatel požadované rozhraní. Po selhání \* `ppvObject` obsahuje `NULL`.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda delegoval vůči `CoCreateInstance`.  
  
## <a name="see-also"></a>Viz také  
 [IRemoteDebugApplication – rozhraní](../../winscript/reference/iremotedebugapplication-interface.md)