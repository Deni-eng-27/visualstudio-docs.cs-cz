---
title: IDebugDocumentContext2::GetLanguageInfo | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugDocumentContext2::GetLanguageInfo
helpviewer_keywords: IDebugDocumentContext2::GetLanguageInfo
ms.assetid: 6a212ee5-414c-4eb5-ab11-19db1786943d
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 3ef815ecde171819fd32ae4a3874fd035492c885
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugdocumentcontext2getlanguageinfo"></a>IDebugDocumentContext2::GetLanguageInfo
Získá jazyk spojený s tímto kontextem dokumentu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetLanguageInfo(   
   BSTR* pbstrLanguage,  
   GUID* pguidLanguage  
);  
```  
  
```csharp  
int GetLanguageInfo(   
   out string pbstrLanguage,  
   out Guid   pguidLanguage  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pbstrLanguage`  
 [out] Vrátí název jazyka, který implementuje kód v tomto kontextu dokumentu.  
  
 `pguidLanguage`  
 [out] Vrátí identifikátor GUID jazyka, který implementuje kód v tomto kontextu dokumentu. Například `guidVBScriptLang` nebo `guidCPPLang`. Tento identifikátor GUID není omezeno na jazyky poskytl [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)].  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak implementovat tuto metodu pro jednoduchou `CDebugContext` objekt, který zveřejňuje [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md) rozhraní.  
  
```cpp  
HRESULT CDebugContext::GetLanguageInfo(BSTR* pbstrLanguage, GUID* pguidLanguage)    
{    
   HRESULT hr;    
  
   // Check for a valid language argument pointers.    
   if (pbstrLanguage && pguidLanguage)    
   {    
      *pguidLanguage = GUID_NULL;    
      *pbstrLanguage = SysAllocString(L"Batch File");    
      if (*pbstrLanguage)    
      {    
         *pguidLanguage = guidBatLang;    
         hr = S_OK;    
      }    
      else    
      {    
         hr = E_OUTOFMEMORY;    
      }    
   }    
   else    
   {    
      hr = E_INVALIDARG;    
   }    
  
   return hr;    
}    
```  
  
## <a name="see-also"></a>Viz také  
 [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md)