---
title: IDebugCodeContext3 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- IDebugCodeContext3 interface
ms.assetid: 524eb882-0ad5-4bfb-95eb-eb3abb3d0237
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: e9ff7ac48c745416dbbed799521048997fba5662
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54956438"
---
# <a name="idebugcodecontext3"></a>IDebugCodeContext3
Rozšiřuje [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md) rozhraní povolit načtení modulu a proces rozhraní.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugCodeContext3 : IDebugCodeContext2  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Pomocí ladicími stroji implementovat a používat [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] ladit balíček.  
  
## <a name="methods"></a>Metody  
 Kromě metod na `IDebugCodeContext2` rozhraní, toto rozhraní implementuje následujících metod:  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetModule](../../../extensibility/debugger/reference/idebugcodecontext3-getmodule.md)|Získá odkaz na rozhraní modulu ladění.|  
|[GetProcess](../../../extensibility/debugger/reference/idebugcodecontext3-getprocess.md)|Získá referenci k rozhraní ladění procesu.|  
  
## <a name="remarks"></a>Poznámky  
 Toto je volitelné rozhraní, která obvykle není nutné implementovat.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: Msdbg.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll