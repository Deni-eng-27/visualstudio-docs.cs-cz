---
title: IDebugApplication::StepOutComplete | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugApplication.StepOutComplete
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugApplication::StepOutComplete
ms.assetid: 9675b214-7be5-4cf7-a63f-7865f3c54371
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 04f8ecfb835199afa0a60f3fde3c8fbdc8812240
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62990619"
---
# <a name="idebugapplicationstepoutcomplete"></a>IDebugApplication::StepOutComplete
Upozorní správce ladění procesu, že modul jazyka v režimu krokování se chystá vrátí výsledek volajícímu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT StepOutComplete();  
```  
  
#### <a name="parameters"></a>Parametry  
 Tato metoda nemá žádné parametry.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
 Jazyk moduly volání této metody v režimu krokování těsně před plánovaným začátkem vrátí jejich volajícímu. Správce ladění procesu používá tuto příležitost upozornit všechny další skriptovacích strojů, které by mělo dojít při první příležitosti. Tato technika je krok jak mezi jazykové režimy jsou implementovány.  
  
## <a name="see-also"></a>Viz také  
 [IDebugApplication – rozhraní](../../winscript/reference/idebugapplication-interface.md)