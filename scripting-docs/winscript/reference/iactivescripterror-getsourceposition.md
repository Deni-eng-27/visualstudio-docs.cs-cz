---
title: IActiveScriptError::GetSourcePosition | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptError.GetSourcePosition
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptError_GetSourcePosition
ms.assetid: ae9b26b1-82a7-4645-9686-3261d8248664
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fb5adfe508b7b5d3de0cf7f508d8c801a36adf1f
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54097367"
---
# <a name="iactivescripterrorgetsourceposition"></a>IActiveScriptError::GetSourcePosition
Získá umístění ve zdrojovém kódu, kde došlo k chybě skriptovací modul byl spuštěn skript.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT GetSourcePosition(  
    DWORD *pdwSourceContext,  // context cookie  
    ULONG *pulLineNumber,     // line number of error  
    LONG *pichCharPosition    // character position of error  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pdwSourceContext`  
 [out] Adresa proměnné, která přijímá soubory cookie, který identifikuje kontextu. Výklad tohoto parametru závisí na hostitelskou aplikaci.  
  
 `pulLineNumber`  
 [out] Adresa proměnné, která přijímá číslo řádku ve zdrojovém souboru, kde došlo k chybě.  
  
 `pichCharPosition`  
 [out] Adresa proměnné, která přijímá pozice znaku v řádku, kde došlo k chybě.  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrátí `S_OK` v případě úspěšného ověření nebo `E_FAIL` Pokud nebyl načten umístění.  
  
## <a name="see-also"></a>Viz také  
 [IActiveScriptError](../../winscript/reference/iactivescripterror.md)