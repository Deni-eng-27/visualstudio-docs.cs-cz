---
title: IDebugSymbolProvider::GetLanguage | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugSymbolProvider::GetLanguage
helpviewer_keywords:
- IDebugSymbolProvider::GetLanguage method
ms.assetid: e4142183-3d8b-418f-907f-4ee4c753d8ce
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: cd5cf44f56b91d5e6c04b220e36c7f0e82d3159c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugsymbolprovidergetlanguage"></a>IDebugSymbolProvider::GetLanguage
Tato metoda získá jazyk, který byl použit pro kompilaci kódu na adrese ladění.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetLanguage(   
   IDebugAddress* pAddress,  
   GUID*          pguidLanguage,  
   GUID*          pguidLanguageVendor  
);  
```  
  
```csharp  
int GetLanguage(  
   IDebugAddress pAddress,   
   out Guid      pguidLanguage,   
   out Guid      pguidLanguageVendor  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pAddress`  
 [v] Objekt adresu reprezentována [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) rozhraní.  
  
 `pguidLanguage`  
 [out] Vrátí `GUID` který určuje jazyk.  
  
 `pguidLanguageVendor`  
 [out] Vrátí `GUID` , který určuje jazyk dodavatele.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Modul ladění volá tuto metodu, pokud chcete získat informace, které potřebuje k výběru vyhodnocovací filtr výrazů správné.  
  
## <a name="see-also"></a>Viz také  
 [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md)   
 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)