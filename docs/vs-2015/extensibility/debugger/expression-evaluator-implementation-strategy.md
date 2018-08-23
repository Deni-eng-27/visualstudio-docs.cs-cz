---
title: Strategie implementace vyhodnocovače výrazů | Dokumentace Microsoftu
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
- expression evaluation, implementation strategy
- debug engines, implementation strategies
ms.assetid: 1bccaeb3-8109-4128-ae79-16fd8fbbaaa2
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 9bb9135dda7b5c8240517efabb3a899022ba1d3d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42628009"
---
# <a name="expression-evaluator-implementation-strategy"></a>Strategie implementace vyhodnocovače výrazů
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [strategie implementace vyhodnocovače výrazů](https://docs.microsoft.com/visualstudio/extensibility/debugger/expression-evaluator-implementation-strategy).  
  
> [!IMPORTANT]
>  V sadě Visual Studio 2015 je zastaralý tímto způsobem implementace vyhodnocovače výrazů. Informace o implementace vyhodnocovače výrazů modulu CLR najdete v tématu [vyhodnocovače výrazů modulu CLR](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) a [spravované ukázka Chyba při vyhodnocování výrazu](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 Jedním z přístupů k rychlému vytváření vyhodnocovače výrazů (EE), je nejprve implementovat minimální kód, který chcete-li zobrazit místní proměnné v **lokální** okna. Je vhodné Pamatujte si, že každý řádek v **lokální** okně se zobrazí název, typ a hodnotu místní proměnné, a všech tří jsou reprezentovány [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) objektu. Název, typ a hodnotu místní proměnné lze získat z `IDebugProperty2` objektu voláním jeho [GetPropertyInfo](../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md) metoda. Další informace o tom, jak zobrazit místní proměnné v **lokální** okna, naleznete v tématu [zobrazení místních hodnot](../../extensibility/debugger/displaying-locals.md).  
  
## <a name="discussion"></a>Diskuse  
 Možnou implementaci sekvence začíná implementace [IDebugExpressionEvaluator](../../extensibility/debugger/reference/idebugexpressionevaluator.md). [Analyzovat](../../extensibility/debugger/reference/idebugexpressionevaluator-parse.md) a [GetMethodProperty](../../extensibility/debugger/reference/idebugexpressionevaluator-getmethodproperty.md) metody potřeba je implementovat do zobrazení místních hodnot. Volání `IDebugExpressionEvaluator::GetMethodProperty` vrátí `IDebugProperty2` objekt, který představuje metodu: to znamená, [IDebugMethodField](../../extensibility/debugger/reference/idebugmethodfield.md) objektu. Metody, samotné se nezobrazují v **lokální** okna.  
  
 [EnumChildren](../../extensibility/debugger/reference/idebugproperty2-enumchildren.md) metoda by měla být implementována dále. Ladicí stroj (DE) volá tuto metodu za účelem získání seznamu místních proměnných a argumentů předáním `IDebugProperty2::EnumChildren` `guidFilter` argument `guidFilterLocalsPlusArgs`. `IDebugProperty2::EnumChildren` volání [EnumArguments](../../extensibility/debugger/reference/idebugmethodfield-enumarguments.md) a [EnumLocals](../../extensibility/debugger/reference/idebugmethodfield-enumlocals.md), kombinaci výsledků v jeden výčet. Zobrazit [zobrazení místních hodnot](../../extensibility/debugger/displaying-locals.md) další podrobnosti.  
  
## <a name="see-also"></a>Viz také  
 [Implementace vyhodnocovače výrazů](../../extensibility/debugger/implementing-an-expression-evaluator.md)   
 [Zobrazení místních hodnot](../../extensibility/debugger/displaying-locals.md)

