---
title: IDebugAlias::GetName | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugAlias::GetName
helpviewer_keywords: IDebugAlias::GetName method
ms.assetid: ac2d8891-56b5-40ef-9866-ed74f18bb043
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 26b9eec300d93695785605549fa109099008d799
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idebugaliasgetname"></a>IDebugAlias::GetName
Získá název tento alias.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetName(  
   BSTR* pbstrName  
);  
```  
  
```csharp  
int GetName(  
   out string pbstrName  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pbstrName`  
 [out] Název aliasu.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí S_OK; jinak vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IDebugAlias](../../../extensibility/debugger/reference/idebugalias.md)