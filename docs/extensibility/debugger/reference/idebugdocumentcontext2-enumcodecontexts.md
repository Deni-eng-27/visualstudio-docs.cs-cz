---
title: IDebugDocumentContext2::EnumCodeContexts | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugDocumentContext2::EnumCodeContexts
helpviewer_keywords:
- IDebugDocumentContext2::EnumCodeContexts
ms.assetid: 627af69c-5cce-4e1d-8233-5f4d8dbc62e5
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: ecb7928342e9ec51432e838b2463280eee22bf00
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54986215"
---
# <a name="idebugdocumentcontext2enumcodecontexts"></a>IDebugDocumentContext2::EnumCodeContexts
Načte seznam všech kontextech kód spojený s tímto kontextem dokumentu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT EnumCodeContexts(   
   IEnumDebugCodeContexts2** ppEnumCodeCxts  
);  
```  
  
```csharp  
int EnumCodeContexts(   
   out IEnumDebugCodeContexts2 ppEnumCodeCxts  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ppEnumCodeCxts`  
 [out] Vrátí [IEnumDebugCodeContexts2](../../../extensibility/debugger/reference/ienumdebugcodecontexts2.md) objekt, který obsahuje seznam kontext kódu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Kontext jednotlivý dokument můžete generovat více kontexty kódu, pokud dokument používá šablony nebo soubory k zahrnutí.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak implementovat tuto metodu pro jednoduchý `CDebugContext` objekt, který zveřejňuje [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md) rozhraní.  
  
```cpp  
HRESULT CDebugContext::EnumCodeContexts(IEnumDebugCodeContexts2 **ppEnumCodeCxts)    
{    
   HRESULT hr;    
  
   // Check for a valid IEnumDebugCodeContexts2 interface pointer.    
   if (ppEnumCodeCxts)    
   {    
      *ppEnumCodeCxts = NULL;    
  
      // Create a CEnumDebugCodeContexts object.    
      CComObject<CEnumDebugCodeContexts>* pEnum;    
      hr = CComObject<CEnumDebugCodeContexts>::CreateInstance(&pEnum);    
      assert(hr == S_OK);    
      if (hr == S_OK)    
      {    
         // Get an IID_IDebugCodeContext2 interface.    
         CComPtr<IDebugCodeContext2> spCodeCxt;    
         hr = QueryInterface(IID_IDebugCodeContext2,  
                             (void**)&spCodeCxt);  
         assert(hr == S_OK);    
         if (hr == S_OK)    
         {    
            // Initialize the code context enumerator with the    
            // IDebugCodeContext2 information.  
            IDebugCodeContext2* rgpCodeContext[] = { spCodeCxt.p };    
            hr = pEnum->Init(rgpCodeContext,  
                             &(rgpCodeContext[1]),  
                             NULL,  
                             AtlFlagCopy);  
            assert(hr == S_OK);    
            if (hr == S_OK)    
            {    
               // Set the passed IEnumDebugCodeContexts2 pointer equal to the pointer  
               // value of the created CEnumDebugCodeContexts object.  
               hr = pEnum->QueryInterface(ppEnumCodeCxts);    
               assert(hr == S_OK);    
            }    
         }    
  
         // Otherwise, delete the CEnumDebugCodeContexts object.    
         if (FAILED(hr))    
         {    
            delete pEnum;    
         }    
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
 [IEnumDebugCodeContexts2](../../../extensibility/debugger/reference/ienumdebugcodecontexts2.md)