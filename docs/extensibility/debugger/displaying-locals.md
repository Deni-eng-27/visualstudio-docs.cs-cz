---
title: Zobrazení místních hodnot | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], expression evaluation
- expression evaluation, displaying locals
ms.assetid: 62264cec-845b-4233-aed7-0b038fa79250
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 3a8a73fb8ab95602538be56f18834233dbad7132
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66345790"
---
# <a name="display-locals"></a>Zobrazení místních hodnot
> [!IMPORTANT]
> V sadě Visual Studio 2015 je zastaralý tímto způsobem implementace vyhodnocovače výrazů. Informace o implementace vyhodnocovače výrazů modulu CLR najdete v tématu [vyhodnocovače výrazů modulu CLR](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) a [ukázka Chyba při vyhodnocování výrazu spravované](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).

 Spuštění vždycky probíhá v rámci metody, označované také jako obsahující metodu nebo aktuální metoda. Při pozastavení provádění volání sady Visual Studio ladicího stroje (DE) zobrazíte seznam místní proměnné a argumenty, se nazývají lokální proměnné metodu. Visual Studio zobrazí tyto místní hodnoty a jejich hodnoty v **lokální** okna.

 Chcete-li zobrazit místní hodnoty, DE volá [GetMethodProperty](../../extensibility/debugger/reference/idebugexpressionevaluator-getmethodproperty.md) metodu, která náleží EE a dá jí kontext vyhodnocení, který je, poskytovatel symbolů (SP), aktuální adresu spuštění a objekt vazače. Další informace najdete v tématu [kontext vyhodnocení](../../extensibility/debugger/evaluation-context.md). Pokud bude volání úspěšné, `IDebugExpressionEvaluator::GetMethodProperty` vrátí metoda [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) objektu, který představuje metodu, která obsahuje aktuální adresu spuštění.

 Volání DE [EnumChildren](../../extensibility/debugger/reference/idebugproperty2-enumchildren.md) zobrazíte [IEnumDebugPropertyInfo2](../../extensibility/debugger/reference/ienumdebugpropertyinfo2.md) objektu, který je filtrovaná, aby vrátit pouze místní hodnoty a přezkoumána za účelem vytvoření seznamu [DEBUG_PROPERTY_INFO](../../extensibility/debugger/reference/debug-property-info.md)struktury. Každá struktura obsahuje název, typ a hodnotu lokální. Typ a hodnota jsou uloženy jako formátovaných řetězců vhodnou k zobrazení. Název, typ a hodnota se obvykle zobrazují společně v jednom řádku **lokální** okna.

> [!NOTE]
> **QuickWatch** a **Watch** proměnné ve stejném formátu název, hodnotu a typ zobrazení systému windows. Ale tyto hodnoty jsou získány pomocí volání [GetPropertyInfo](../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md) místo `IDebugProperty2::EnumChildren`.

## <a name="in-this-section"></a>V tomto oddílu
 [Ukázková implementace místních hodnot](../../extensibility/debugger/sample-implementation-of-locals.md) se používají příklady pro jednotlivé kroky v procesu implementace místních hodnot.

## <a name="related-sections"></a>Související oddíly
 [Kontext vyhodnocení](../../extensibility/debugger/evaluation-context.md) vysvětluje, že když se ladicí stroj (DE) volá vyhodnocovací filtr výrazů (EE), předá tři argumenty.

## <a name="see-also"></a>Viz také:
 [Zápis vyhodnocovací filtr výrazů modulu CLR](../../extensibility/debugger/writing-a-common-language-runtime-expression-evaluator.md)