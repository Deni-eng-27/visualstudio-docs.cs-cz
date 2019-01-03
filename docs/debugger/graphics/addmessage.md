---
title: AddMessage | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 102a0404-a00c-4566-93f3-01bc8df63280
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6555072bcbebe24011ca0701f02f48bc1703c34a
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53985732"
---
# <a name="addmessage"></a>AddMessage
Přidá vlastní zprávu pro diagnostiku grafiky *HUD* (zobrazení vedoucí nahoru).  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
void AddMessage(  
  wchar_t const * szMessage  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `szMessage`  
 Zpráva, která mají být přidány do HUD.  
  
## <a name="remarks"></a>Poznámky  
 HUD Diagnostika grafiky se zobrazí v levém horním rohu aplikace, na kterém běží v rámci diagnostiky grafiky. Zobrazuje běhové informace o aplikaci a o zachycení informací grafiky a zprávy, které jsou přidány pomocí volání této funkce.  
  
 K přidání zprávy do HUD, nemusíte být aktivně zachycení informací grafiky – to znamená, je možné přidat zprávu prostřednictvím instance `VsgDbg` třídy, ale [Init](init.md) členská funkce nevytváří nejprve volat. Zprávy se zobrazují jenom v HUD, se zaznamenávají do souboru protokolu grafiky.