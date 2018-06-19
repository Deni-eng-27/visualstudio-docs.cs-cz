---
title: IDebugProperty2::GetDerivedMostProperty | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugProperty2::GetDerivedMostProperty
helpviewer_keywords:
- IDebugProperty2::GetDerivedMostProperty
ms.assetid: cc86b461-62d1-4340-8209-c65037fd8b02
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: f453dacf988b80cf6837b3324a9d4b0a70e2254e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31116705"
---
# <a name="idebugproperty2getderivedmostproperty"></a>IDebugProperty2::GetDerivedMostProperty
Získá vlastnost odvozené většinu vlastnosti.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetDerivedMostProperty (   
   IDebugProperty2** ppDerivedMost  
);  
```  
  
```csharp  
int GetDerivedMostProperty (   
   out IDebugProperty2 ppDerivedMost  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ppDerivedMost`  
 [out] Vrátí [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) objekt, který reprezentuje vlastnost odvozené nejvíc.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`; v opačném případě vrátí kód chyby. Vrátí `S_GETDERIVEDMOST_NO_DERIVED_MOST` Pokud není žádná vlastnost odvozené většinu k načtení.  
  
## <a name="remarks"></a>Poznámky  
 Například, pokud je tato vlastnost popisuje objekt, který implementuje `ClassRoot` , ale který je ve skutečnosti vytváření instancí z `ClassDerived` je odvozena z `ClassRoot`, pak tato metoda vrátí [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) objektu popisující `ClassDerived` objektu.  
  
## <a name="see-also"></a>Viz také  
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)