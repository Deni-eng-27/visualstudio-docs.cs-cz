---
title: IDebugCustomAttributeQuery2::IsCustomAttributeDefined | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugCustomAttributeQuery2::IsCustomAttributeDefined
helpviewer_keywords:
- IDebugCustomAttributeQuery2::IsCustomAttributeDefined
ms.assetid: 5c07cc52-6d2d-42df-9d76-9f1f769641db
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: ed07afde1db8aa99ce8edea093abd9bf25c069d6
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idebugcustomattributequery2iscustomattributedefined"></a>IDebugCustomAttributeQuery2::IsCustomAttributeDefined
Určuje, zda existuje vlastní atribut podle názvu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT IsCustomAttributeDefined(   
   LPCOLESTR pszCustomAttributeName  
);  
```  
  
```csharp  
int IsCustomAttributeDefined(  
   [In] string pszCustomAttributeName  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pszCustomAttributeName`  
 [v] Řetězec obsahující název pro vlastní atribut najít.  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrátí že S_OK Pokud vlastní atribut je definován na toto pole, v opačném případě vrátí S_FALSE.  
  
## <a name="remarks"></a>Poznámky  
 Chcete-li získat bajtů atribut přidružený vlastních atributů, zavolejte [getcustomattributebyname –](../../../extensibility/debugger/reference/idebugcustomattributequery2-getcustomattributebyname.md) metoda.  
  
## <a name="see-also"></a>Viz také  
 [IDebugCustomAttributeQuery2](../../../extensibility/debugger/reference/idebugcustomattributequery2.md)