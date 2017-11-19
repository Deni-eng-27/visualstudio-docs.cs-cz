---
title: "Ukázkové implementace vyhodnocení výrazu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- expression evaluators
- debugging [Debugging SDK], expression evaluators
- expression evaluation, examples
ms.assetid: 2a5f04b8-6c65-4232-bddd-9093653a22c4
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 2cae1e8d697ba8079b29fa2188f0fb2f8b9a40e6
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="sample-implementation-of-expression-evaluation"></a>Ukázka implementace vyhodnocení výrazu
> [!IMPORTANT]
>  V sadě Visual Studio 2015 se již nepoužívá tímto způsobem implementace vyhodnocovače výrazů. Informace o implementaci vyhodnocovače výrazů CLR, najdete v tématu [vyhodnocovače výrazů CLR](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) a [spravované ukázka vyhodnocování výrazu](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 Pro **sledovat** okno výrazu, Visual Studio volání [ParseText](../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) k vytvoření [IDebugExpression2](../../extensibility/debugger/reference/idebugexpression2.md) objektu. `IDebugExpressionContext2::ParseText`vytvoří instanci (EE) vyhodnocovací filtr výrazů a volání [analyzovat](../../extensibility/debugger/reference/idebugexpressionevaluator-parse.md) získat [IDebugParsedExpression](../../extensibility/debugger/reference/idebugparsedexpression.md) objektu.  
  
 Tato implementace `IDebugExpressionEvaluator::Parse` provede následující úlohy:  
  
1.  [Pouze C++] Analyzuje výraz, který se vyhledejte chyby.  
  
2.  Vytvoří instanci třídy (nazývá `CParsedExpression` v tomto příkladu), která implementuje `IDebugParsedExpression` rozhraní a ukládá ve třídě výraz, který má být analyzován.  
  
3.  Vrátí `IDebugParsedExpression` rozhraní z `CParsedExpression` objektu.  
  
> [!NOTE]
>  V příkladech, které následují a v ukázce MyCEE vyhodnocovací filtr výrazů není samostatné analýza z vyhodnocení.  
  
## <a name="managed-code"></a>Spravovaný kód  
 To je implementací `IDebugExpressionEvaluator::Parse` ve spravovaném kódu. Všimněte si, že tato verze metody odkládat údaje analýza k [EvaluateSync](../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md) jako kód pro analýzu také vyhodnotí ve stejnou dobu (v tématu [vyhodnocení výrazu](../../extensibility/debugger/evaluating-a-watch-expression.md)).  
  
```csharp  
namespace EEMC  
{  
    public class CParsedExpression : IDebugParsedExpression  
    {  
        public HRESULT Parse(  
                string                 expression,   
                uint                   parseFlags,  
                uint                   radix,  
            out string                 errorMessage,   
            out uint                   errorPosition,   
            out IDebugParsedExpression parsedExpression)  
        {   
            errorMessage = "";  
            errorPosition = 0;  
  
            parsedExpression =  
                new CParsedExpression(parseFlags, radix, expression);  
            return COM.S_OK;  
        }  
    }  
}  
```  
  
## <a name="unmanaged-code"></a>Nespravovaný kód  
 To je implementací `IDebugExpressionEvaluator::Parse` v nespravovaném kódu. Tato metoda volá podpůrná funkce `Parse`, analyzovat výraz a zkontrolujte chyby, ale tato metoda ignoruje výslednou hodnotu. Je k odložení formální vyhodnocení [EvaluateSync](../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md) kde je výraz analyzovat při vyhodnotí (najdete v části [vyhodnocení výrazu](../../extensibility/debugger/evaluating-a-watch-expression.md)).  
  
```cpp  
STDMETHODIMP CExpressionEvaluator::Parse(  
        in    LPCOLESTR                 pszExpression,  
        in    PARSEFLAGS                flags,  
        in    UINT                      radix,  
        out   BSTR                     *pbstrErrorMessages,  
        inout UINT                     *perrorCount,  
        out   IDebugParsedExpression  **ppparsedExpression  
    )  
{  
    if (pbstrErrorMessages == NULL)  
        return E_INVALIDARG;  
    else  
        *pbstrErrormessages = 0;  
  
    if (pparsedExpression == NULL)  
        return E_INVALIDARG;  
    else  
        *pparsedExpression = 0;  
  
    if (perrorCount == NULL)  
        return E_INVALIDARG;  
  
    HRESULT hr;  
    // Look for errors in the expression but ignore results  
    hr = ::Parse( pszExpression, pbstrErrorMessages );  
    if (hr != S_OK)  
        return hr;  
  
    CParsedExpression* pparsedExpr = new CParsedExpression( radix, flags, pszExpression );  
    if (!pparsedExpr)  
        return E_OUTOFMEMORY;  
  
    hr = pparsedExpr->QueryInterface( IID_IDebugParsedExpression,  
                                      reinterpret_cast<void**>(ppparsedExpression) );  
    pparsedExpr->Release();  
  
    return hr;  
}  
```  
  
## <a name="see-also"></a>Viz také  
 [Vyhodnocení výrazu okno kukátka](../../extensibility/debugger/evaluating-a-watch-window-expression.md)   
 [Vyhodnocení výrazu](../../extensibility/debugger/evaluating-a-watch-expression.md)