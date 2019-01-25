---
title: IDebugCodeContext3 | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
helpviewer_keywords:
- IDebugCodeContext3 interface
ms.assetid: 524eb882-0ad5-4bfb-95eb-eb3abb3d0237
caps.latest.revision: 9
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 62b84bd77038c7a17b65f764bd303d6a6372a52c
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54805343"
---
# <a name="idebugcodecontext3"></a>IDebugCodeContext3
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Rozšiřuje [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md) rozhraní povolit načtení modulu a proces rozhraní.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugCodeContext3 : IDebugCodeContext2  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Pomocí ladicími stroji implementovat a používat [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] ladit balíček.  
  
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
