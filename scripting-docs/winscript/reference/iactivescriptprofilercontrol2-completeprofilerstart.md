---
title: IActiveScriptProfilerControl2::CompleteProfilerStart | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IActiveScriptProfilerControl2::CompleteProfilerStart
ms.assetid: e14d94a2-39d3-40a1-84d9-6300fbe2b339
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 36a1f5d6a1401e2860b65a29c8e383627e83c6be
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62993021"
---
# <a name="iactivescriptprofilercontrol2completeprofilerstart"></a>IActiveScriptProfilerControl2::CompleteProfilerStart
Oznámí profileru, které jste spustili profilaci na všechny příslušné skriptovacích strojů. Tímto způsobem můžete získat úplný zásobník volání, pokud [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] je spuštěna při spuštění profilace.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT CompleteProfilerStart();  
```  
  
#### <a name="parameters"></a>Parametry  
 Metoda nepřijímá žádné parametry.  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrátí hodnotu HRESULT. Možné hodnoty jsou následující:  
  
|Návratová hodnota|Význam|  
|------------------|-------------|  
|`S_OK`|Metoda byla úspěšná.|  
|`E_FAIL`|Nelze spustit profilaci.|  
|`S_FALSE`|Profilace byla spuštěna, když skript nebyl spuštěn.|  
|`ACTIVPROF_E_PROFILER_ABSENT`|Profilace není povolená. Byl nastaven bez zpětného volání.|  
|`E_OUTOFMEMORY`|Z důvodu podmínku na více instancí z důvodu nedostatku paměti nelze získat zásobník volání.|  
  
## <a name="remarks"></a>Poznámky  
 Volání `IActiveScriptProfilerControl2::CompleteProfilerStart` zajistí, že jsou odesílány události pro funkce již v zásobníku volání. Tato metoda se má volat po procesu profilace spouští na libovolné skriptovací stroj, který je na aktuální kartě. Metodu lze volat pro jakékoli skriptovací stroj.  
  
## <a name="see-also"></a>Viz také  
 [IActiveScriptProfilerControl2::PrepareProfilerStop](../../winscript/reference/iactivescriptprofilercontrol2-prepareprofilerstop.md)   
 [IActiveScriptProfilerControl2 – rozhraní](../../winscript/reference/iactivescriptprofilercontrol2-interface.md)