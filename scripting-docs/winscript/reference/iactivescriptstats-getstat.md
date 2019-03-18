---
title: IActiveScriptStats::GetStat | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptStats.GetStat
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptStats::GetStat
ms.assetid: 31fd15b3-0713-4b55-b4f7-bfd7ea198493
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8befb3da4e4b6f060a5f58aedec3604afe70aefb
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58159046"
---
# <a name="iactivescriptstatsgetstat"></a>IActiveScriptStats::GetStat
Vrátí jednu standardní skript statistiky.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT GetStat(  
   DWORD   stid,  
   ULONG*  pluHi,  
   ULONG*  pluLo  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `stid`  
 [in] Určuje, které statistiku k vrácení. Hodnota musí být:  
  
|Konstanta|Hodnota|Popis|  
|--------------|-----------|-----------------|  
|SCRIPTSTAT_STATEMENT_COUNT|1|Vrátí počet příkazů provést, protože spuštění skriptu nebo statistiku bylo obnoveno.|  
  
 `pluHi`  
 [out] Vysoká 32 bitů 64bitové celé číslo bez znaménka představující statistiky.  
  
 `pluLo`  
 [out] Nízká 32 bitů 64bitové celé číslo bez znaménka představující statistiky.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty patří, ale nejsou omezeny pouze na hodnoty v následující tabulce.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda vrátí jednu standardní skript statistiky.  
  
## <a name="see-also"></a>Viz také  
 [IActiveScriptStats::GetStatEx](../../winscript/reference/iactivescriptstats-getstatex.md)   
 [IActiveScriptStats – rozhraní](../../winscript/reference/iactivescriptstats-interface.md)