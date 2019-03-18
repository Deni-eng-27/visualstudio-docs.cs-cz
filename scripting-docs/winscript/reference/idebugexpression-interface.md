---
title: Idebugexpression – rozhraní | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDebugExpression interface
ms.assetid: 36c00ffb-7160-4c30-a2c9-c9d70c8213cd
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 589c231afbc149c4eeface784d3cdbd43c4e5e40
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58156343"
---
# <a name="idebugexpression-interface"></a>IDebugExpression – rozhraní
Představuje asynchronně vyhodnocený výraz. Toto rozhraní implementují obvykle skriptovací stroje. Toto rozhraní IDE ladicí program obvykle používá k povolení okamžité spuštění okna nebo okno kukátka.  
  
> [!NOTE]
>  `IDebugExpression` Rozhraní je k dispozici pouze v rámci zásobníku.  
  
 Kromě metod zděděných z `IUnknown`, `IDebugExpression` rozhraní poskytuje následující metody.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IDebugExpression::Start](../../winscript/reference/idebugexpression-start.md)|Zahájí vyhodnocení výrazu.|  
|[IDebugExpression::Abort](../../winscript/reference/idebugexpression-abort.md)|Zruší výraz.|  
|[IDebugExpression::QueryIsComplete](../../winscript/reference/idebugexpression-queryiscomplete.md)|Určuje, zda je operace dokončena.|  
|[IDebugExpression::GetResultAsString](../../winscript/reference/idebugexpression-getresultasstring.md)|Vrátí výsledek vyhodnocení výrazu jako řetězec a návratová hodnota operace.|  
|[IDebugExpression::GetResultAsDebugProperty](../../winscript/reference/idebugexpression-getresultasdebugproperty.md)|Vrátí výsledek vyhodnocení výrazu jako vlastnost ladění a návratová hodnota operace.|