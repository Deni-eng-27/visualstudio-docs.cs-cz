---
title: Ijsdebug::openvirtualprocess – metoda | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IJSDebug.OpenVirtualProcess
apilocation:
- jscript9diag.dll
ms.assetid: 5612bf1b-a4e3-4eaf-ac5e-c2e1f147c395
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: daa5414153ee55a431294afaf7b167ee91839bfc
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54093987"
---
# <a name="ijsdebugopenvirtualprocess-method"></a>IJsDebug::OpenVirtualProcess – metoda
Metody výroby použité k vytvoření nového objektu virtuálního procesu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT OpenVirtualProcess(  
   DWORD processId,  
   UINT64 runtimeJsBaseAddress,  
   IJsDebugDataTarget *pDataTarget,  
   IJsDebugProcess **ppProcess  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `processId`  
 [in] Id procesu připojit ladicí program.  
  
 `runtimeJsBaseAddress`  
 [in] Základní adresa, na které modulu runtime jazyka JavaScript načítal do cílového procesu.  
  
 `pDataTarget`  
 [in] Ladicí program zadané rozhraní pro dotaz na stav procesu.  
  
 `ppProcess`  
 [out] Nový objekt procesu ladění  
  
## <a name="return-value"></a>Návratová hodnota  
  
## <a name="remarks"></a>Poznámky  
 Vrátí E_JsDEBUG_MISMATCHED_RUNTIME, pokud Jscript9diag a Jscript9 se neshodují.  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** jscript9diag.h  
  
## <a name="see-also"></a>Viz také  
 [IJsDebug – rozhraní](../../winscript/reference/ijsdebug-interface.md)