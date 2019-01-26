---
title: IDebugAlias::Dispose | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugAlias::Dispose
helpviewer_keywords:
- IDebugAlias::Dispose method
ms.assetid: e84909a4-d378-4f48-bf25-2c014c77c8e3
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: f5dffc8e9bb5440fb1a05cd733c609af43104f72
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55028410"
---
# <a name="idebugaliasdispose"></a>IDebugAlias::Dispose
Označí tento alias pro odebrání.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT Dispose();  
```  
  
```csharp  
int Dispose();  
```  
  
#### <a name="parameters"></a>Parametry  
 Žádné  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí hodnotu S_OK; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Když tato metoda je volána, alias není nadále k dispozici.  
  
## <a name="see-also"></a>Viz také  
 [IDebugAlias](../../../extensibility/debugger/reference/idebugalias.md)