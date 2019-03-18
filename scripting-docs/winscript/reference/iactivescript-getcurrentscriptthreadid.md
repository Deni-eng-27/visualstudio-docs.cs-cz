---
title: IActiveScript::GetCurrentScriptThreadID | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScript.GetCurrentScriptThreadID
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScript_GetCurrentScriptThreadID
ms.assetid: b09e8b48-4209-480e-8b71-e99ee9ae2e17
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9e1b6e7bae7d78c18e11cd1aac8d0844fb9e90a5
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58152246"
---
# <a name="iactivescriptgetcurrentscriptthreadid"></a>IActiveScript::GetCurrentScriptThreadID
Načte identifikátor skriptovací stroj definované pro aktuálně spuštěné vlákno. Identifikátor lze použít v následných voláních metody řízení provádění vlákna skriptů, jako [IActiveScript::InterruptScriptThread](../../winscript/reference/iactivescript-interruptscriptthread.md) metody.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT GetCurrentScriptThreadID(  
    SCRIPTTHREADID *pstidThread  // receives scripting thread identifier  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pstidThread`  
 [out] Adresa proměnné, který přijímají identifikátor vlákna skript, který je spojený s aktuálním vláknem. Výklad tohoto identifikátoru je ponecháno na skriptovací stroj, ale může být pouze kopie identifikátor Windows. Pokud vlákno Win32 skončí, tento identifikátor se stane nepřiřazené a následně je možné přiřadit k jiné vlákno.  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrátí `S_OK` v případě úspěšného ověření nebo `E_POINTER` Pokud byl zadán neplatný ukazatel.  
  
## <a name="remarks"></a>Poznámky  
 Tuto metodu lze volat z vlákna znaky bez výsledkem znaky popisek hostitele objektů nebo [iactivescriptsite –](../../winscript/reference/iactivescriptsite.md) rozhraní.  
  
## <a name="see-also"></a>Viz také  
 [IActiveScript](../../winscript/reference/iactivescript.md)