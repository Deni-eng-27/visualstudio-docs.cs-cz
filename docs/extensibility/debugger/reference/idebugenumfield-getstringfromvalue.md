---
title: IDebugEnumField::GetStringFromValue | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugEnumField::GetStringFromValue
helpviewer_keywords: IDebugEnumField::GetStringFromValue method
ms.assetid: 5f95fd0c-fdce-497f-9f54-2ad8749494e9
caps.latest.revision: "5"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: ed010734ec09af01c4a7abe6f8ceab0a93fdb482
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idebugenumfieldgetstringfromvalue"></a>IDebugEnumField::GetStringFromValue
Tato metoda získá název konstanta výčtu zadány jeho hodnota.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetStringFromValue(  
   ULONGLONG value,  
   BSTR*     pbstrValue  
);  
```  
  
```csharp  
int GetStringFromValue(  
   ulong      value,  
   out string pbstrValue  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `value`  
 [v] Hodnota, pro které chcete získat název výčtu konstantní.  
  
 `pbstrValue`  
 [out] Vrací název konstanta výčtu.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí `S_FALSE` Pokud hodnota nemá žádný související název nebo vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Pokud existuje více než jeden název spojený se stejnou hodnotou, bude vrácen první název definovaný ve výčtu.  
  
## <a name="see-also"></a>Viz také  
 [IDebugEnumField](../../../extensibility/debugger/reference/idebugenumfield.md)