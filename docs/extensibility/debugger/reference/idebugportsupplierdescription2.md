---
title: IDebugPortSupplierDescription2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IDebugPortSupplierDescription2 interface
ms.assetid: dd19b9d6-0703-44b3-9498-cedffa0ce5b7
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: d4fe70f9d0ef5273f30f16e99524247a2e45843c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugportsupplierdescription2"></a>IDebugPortSupplierDescription2
Umožňuje [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] uživatelského rozhraní k zobrazení textu uvnitř **přenosu informací** části **připojit k procesu** dialogové okno.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugPortSupplierDescription2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Toto rozhraní je implementováno modulem dodavatelé portu.  
  
## <a name="methods"></a>Metody  
 Následující tabulka uvádí metody `IDebugPortSupplierDescription2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetDescription](../../../extensibility/debugger/reference/idebugportsupplierdescription2-getdescription.md)|Načte popis a popis metadata pro dodavatele portu.|  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: Msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll