---
title: IDebugReference2::GetDerivedMostReference | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugReference2::GetDerivedMostReference
helpviewer_keywords:
- IDebugReference2::GetDerivedMostReference
ms.assetid: 07253b74-7d39-48e0-8e85-ac8dfd919f6e
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 0427b9e8dcd4cd21fd6c1514d7b7ce80596678e7
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54971059"
---
# <a name="idebugreference2getderivedmostreference"></a>IDebugReference2::GetDerivedMostReference
Získá odkaz na nejvíce odvozené odkaz. Vyhrazeno pro budoucí použití.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetDerivedMostReference(   
   IDebugReference2** ppDerivedMost  
);  
```  
  
```csharp  
int GetDerivedMostReference(   
   out IDebugReference2 ppDerivedMost  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ppDerivedMost`  
 [out] Vrátí [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md) objekt, který reprezentuje vlastnost nejvíce odvozené.  
  
## <a name="return-value"></a>Návratová hodnota  
 Vždy vrátí `E_NOTIMPL`.  
  
## <a name="remarks"></a>Poznámky  
 Například, pokud je tato vlastnost popisuje objekt, který implementuje `ClassRoot` , ale která je ve skutečnosti instance `ClassDerived` , která je odvozena od `ClassRoot`, pak tato metoda vrátí [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md) objektu představuje odkaz na `ClassDerived` objektu.  
  
## <a name="see-also"></a>Viz také  
 [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)