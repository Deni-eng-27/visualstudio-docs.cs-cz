---
title: IActiveScript::GetScriptThreadID | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScript.GetScriptThreadID
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScript_GetScriptThreadID
ms.assetid: 2595d76e-30b5-429f-88b4-1d026645dd9b
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7b1c68d60b827e7540711cdf6ba34260fb8642ed
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54094871"
---
# <a name="iactivescriptgetscriptthreadid"></a>IActiveScript::GetScriptThreadID
Načte identifikátor skriptovací stroj definované pro vlákno přidružené k dané vlákno Win32.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT GetScriptThreadID(  
    DWORD dwWin32ThreadID,       // Win32 thread identifier.  
    SCRIPTTHREADID *pstidThread  // Receives scripting thread. identifier  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `dwWin32ThreadID` ,  
 [in] Identifikátor vlákna spuštěné vlákno Win32 v aktuálním procesu. Použití [IActiveScript::GetCurrentScriptThreadID](../../winscript/reference/iactivescript-getcurrentscriptthreadid.md) funkce načtete identifikátor aktuálně spuštěné vlákno.  
  
 `pstidThread` ,  
 [out] Adresa proměnné, který přijímají identifikátor vlákna skript, který je přidružený k dané vlákno Win32. Výklad tohoto identifikátoru je ponecháno na skriptovací stroj, ale může být pouze kopie identifikátor Windows. Všimněte si, že pokud skončí, vlákno Win32, tento identifikátor se stane nepřiřazené a následně může být přiřazen jiné vlákno.  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrátí jednu z následujících hodnot:  
  
|Návratová hodnota|Význam|  
|------------------|-------------|  
|`S_OK`|Úspěch.|  
|`E_POINTER`|Byl zadán neplatný ukazatel.|  
|`E_UNEXPECTED`|Volání nebylo očekáváno (například skriptovací stroj má ještě nebyly načteny nebo inicializován) a proto se nezdařilo.|  
  
## <a name="remarks"></a>Poznámky  
 Načtené identifikátor lze použít v následných voláních metody řízení provádění vlákna skriptů, jako [IActiveScript::InterruptScriptThread](../../winscript/reference/iactivescript-interruptscriptthread.md) metody.  
  
 Tuto metodu lze volat z vlákna znaky bez výsledkem znaky popisek hostitele objektů nebo [IActiveScript::InterruptScriptThread](../../winscript/reference/iactivescript-interruptscriptthread.md) rozhraní.  
  
## <a name="see-also"></a>Viz také  
 [IActiveScript](../../winscript/reference/iactivescript.md)