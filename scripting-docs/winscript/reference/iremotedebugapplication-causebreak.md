---
title: IRemoteDebugApplication::CauseBreak | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IRemoteDebugApplication.CauseBreak
apilocation:
- pdm.dll
helpviewer_keywords:
- IRemoteDebugApplication::CauseBreak
ms.assetid: 6a2c27bb-dca0-475c-9918-bdbb70a50d26
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ce0ebe3b32b11bdd79884504233b3f4e09a035f8
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58154150"
---
# <a name="iremotedebugapplicationcausebreak"></a>IRemoteDebugApplication::CauseBreak
Způsobí, že aplikace do ladicího programu při nejbližší příležitosti.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT CauseBreak();  
```  
  
#### <a name="parameters"></a>Parametry  
 Tato metoda nemá žádné parametry.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
 Voláním této metody nezpůsobí okamžité přerušení aplikace. Pokud aplikace aktuálně nezpracovává kód skriptu, dlouhou dobu může uplynout, než aplikace ve skutečnosti zastaví.  
  
## <a name="see-also"></a>Viz také  
 [IRemoteDebugApplication – rozhraní](../../winscript/reference/iremotedebugapplication-interface.md)