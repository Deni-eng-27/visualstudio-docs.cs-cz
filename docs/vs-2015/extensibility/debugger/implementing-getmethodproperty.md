---
title: Implementace GetMethodProperty | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- GetMethodProperty method
- IDebugExpressionEvaluator2 property
ms.assetid: 6305874f-a2c4-4432-834c-07530ea84bff
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 5a995def1c8776a823183b28625fc406772f625d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42670048"
---
# <a name="implementing-getmethodproperty"></a>Implementace GetMethodProperty
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [implementace GetMethodProperty](https://docs.microsoft.com/visualstudio/extensibility/debugger/implementing-getmethodproperty).  
  
> [!IMPORTANT]
>  V sadě Visual Studio 2015 je zastaralý tímto způsobem implementace vyhodnocovače výrazů. Informace o implementace vyhodnocovače výrazů modulu CLR najdete v tématu [vyhodnocovače výrazů modulu CLR](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) a [spravované ukázka Chyba při vyhodnocování výrazu](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 Visual Studio volá stroje ladění (DE) [GetDebugProperty](../../extensibility/debugger/reference/idebugstackframe2-getdebugproperty.md), která pak volá [GetMethodProperty](../../extensibility/debugger/reference/idebugexpressionevaluator-getmethodproperty.md) získat informace o aktuální metoda na zásobníku.  
  
 Tato implementace `IDebugExpressionEvaluator::GetMethodProperty` provádí následující úlohy:  
  
1.  Volání [GetContainerField](../../extensibility/debugger/reference/idebugsymbolprovider-getcontainerfield.md), předejte [IDebugAddress](../../extensibility/debugger/reference/idebugaddress.md) objektu. Poskytovatel symbolů (SP) vrátí [IDebugContainerField](../../extensibility/debugger/reference/idebugcontainerfield.md) představující metodu, která obsahuje zadané adrese.  
  
2.  Získává [IDebugMethodField](../../extensibility/debugger/reference/idebugmethodfield.md) z `IDebugContainerField`.  
  
3.  Vytvoří instanci třídy (volá `CFieldProperty` v tomto příkladu), který implementuje [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) rozhraní a obsahuje `IDebugMethodField` objekt se vrátil ze žádostí  
  
4.  Vrátí `IDebugProperty2` rozhraní z `CFieldProperty` objektu.  
  
## <a name="managed-code"></a>Spravovaný kód  
 Tento příklad ukazuje implementaci `IDebugExpressionEvaluator::GetMethodProperty` ve spravovaném kódu.  
  
```csharp  
namespace EEMC  
{  
    [GuidAttribute("462D4A3D-B257-4AEE-97CD-5918C7531757")]  
    public class EEMCClass : IDebugExpressionEvaluator  
    {  
        public HRESULT GetMethodProperty(  
                IDebugSymbolProvider symbolProvider,  
                IDebugAddress        address,  
                IDebugBinder         binder,  
                int                  includeHiddenLocals,  
            out IDebugProperty2      property)   
        {  
            IDebugContainerField containerField = null;  
            IDebugMethodField methodField       = null;  
            property = null;  
  
            // Get the containing method field.  
            symbolProvider.GetContainerField(address, out containerField);  
            methodField = (IDebugMethodField) containerField;  
  
            // Return the property of method field.  
            property = new CFieldProperty(symbolProvider, address, binder, methodField);  
            return COM.S_OK;  
        }  
    }  
}  
```  
  
## <a name="unmanaged-code"></a>Nespravovaný kód  
 Tento příklad ukazuje implementaci `IDebugExpressionEvaluator::GetMethodProperty` v nespravovaném kódu.  
  
```  
[CPP]  
STDMETHODIMP CExpressionEvaluator::GetMethodProperty(  
        in IDebugSymbolProvider *pprovider,  
        in IDebugAddress        *paddress,  
        in IDebugBinder         *pbinder,  
        in BOOL                  includeHiddenLocals,  
        out IDebugProperty2    **ppproperty  
    )  
{  
    if (pprovider == NULL)  
        return E_INVALIDARG;  
  
    if (ppproperty == NULL)  
        return E_INVALIDARG;  
    else  
        *ppproperty = 0;  
  
    HRESULT hr;  
    IDebugContainerField* pcontainer = NULL;  
  
    hr = pprovider->GetContainerField(paddress, &pcontainer);  
    if (FAILED(hr))  
        return hr;  
  
    IDebugMethodField*    pmethod    = NULL;  
    hr = pcontainer->QueryInterface( IID_IDebugMethodField,  
            reinterpret_cast<void**>(&pmethod));  
    pcontainer->Release();  
    if (FAILED(hr))  
        return hr;  
  
    CFieldProperty* pfieldProperty = new CFieldProperty( pprovider,  
                                                         paddress,  
                                                         pbinder,  
                                                         pmethod );  
    pmethod->Release();  
    if (!pfieldProperty)  
        return E_OUTOFMEMORY;  
  
    hr = pfieldProperty->Init();  
    if (FAILED(hr))  
    {  
        pfieldProperty->Release();  
        return hr;  
    }  
  
    hr = pfieldProperty->QueryInterface( IID_IDebugProperty2,  
            reinterpret_cast<void**>(ppproperty));  
    pfieldProperty->Release();  
  
    return hr;  
}  
```  
  
## <a name="see-also"></a>Viz také  
 [Ukázková implementace místních hodnot](../../extensibility/debugger/sample-implementation-of-locals.md)

