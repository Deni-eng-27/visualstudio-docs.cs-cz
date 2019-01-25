---
title: Setwefprocessid – metoda
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 7807d0495c5f0548178b1bc2ecae12d57cc3b072
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/24/2019
ms.locfileid: "54876119"
---
# <a name="setwefprocessid-method"></a>Setwefprocessid – metoda
  Poskytuje identifikátor procesu, který se spustí rozšíření webové rozhraní Framework (WEF) obsah.  
  
## <a name="syntax"></a>Syntaxe  
  
```csharp  
HRESULT SetWefProcessId(  
    [in] DWORD dwProcessId  
);  
```  
  
#### <a name="parameters"></a>Parametry  
  
|Parametr|Popis|  
|---------------|-----------------|  
|*dwProcessId*|Identifikátor procesu, který se použije ke spuštění WEF obsah.|  
  
## <a name="return-value"></a>Návratová hodnota  
 Hodnota HRESULT, která označuje, zda metoda byla úspěšně dokončena.  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda musí být volána po procesu WEF obsahu, ale před spuštěním jakéhokoli WEF obsahu.  
  
 Pokud chcete připojit ladicí program k procesu obsahu WEF vývojové prostředí, musí prostředí ve vaší implementaci této metody provedení této operace.  
