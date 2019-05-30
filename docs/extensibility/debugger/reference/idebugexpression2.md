---
title: IDebugExpression2 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugExpression2
helpviewer_keywords:
- IDebugExpression2 interface
ms.assetid: f5e4b124-1e30-47c8-a511-80084a02dba5
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 694db3cc5292f11f1718a51e31deec4a8e456b54
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66325969"
---
# <a name="idebugexpression2"></a>IDebugExpression2
Toto rozhraní představuje analyzovaný výraz připravené pro vazby a hodnocení.

## <a name="syntax"></a>Syntaxe

```
IDebugExpression2 : IUnknown
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 Ladicí stroj (DE) implementuje toto rozhraní k reprezentaci výrazu analyzovaný připraven k vyhodnocení.

## <a name="notes-for-callers"></a>Poznámky pro volající
 Volání [ParseText](../../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) vrátí toto rozhraní. [GetExpressionContext](../../../extensibility/debugger/reference/idebugstackframe2-getexpressioncontext.md) vrátí [IDebugExpressionContext2](../../../extensibility/debugger/reference/idebugexpressioncontext2.md) rozhraní. Tato rozhraní jsou přístupné pouze v případě, že byl pozastaven laděnému programu a rámec zásobníku je k dispozici.

## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí
 V následující tabulce jsou uvedeny metody objektu `IDebugExpression2`.

|Metoda|Popis|
|------------|-----------------|
|[EvaluateAsync](../../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md)|Tento výraz vyhodnotí asynchronně.|
|[Abort](../../../extensibility/debugger/reference/idebugexpression2-abort.md)|Ukončí asynchronní výraz hodnocení.|
|[EvaluateSync](../../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md)|Tento výraz vyhodnotí synchronně.|

## <a name="remarks"></a>Poznámky
 Když program se zastavil, Správce ladění relace (SDM) získává rámec zásobníku z DE voláním [EnumFrameInfo](../../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md). Pak zavolá SDM [GetExpressionContext](../../../extensibility/debugger/reference/idebugstackframe2-getexpressioncontext.md) zobrazíte [IDebugExpressionContext2](../../../extensibility/debugger/reference/idebugexpressioncontext2.md) rozhraní. Následuje volání [ParseText](../../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) vytvořit `IDebugExpression2` rozhraní, které představuje analyzovaný výraz, který je připravený k vyhodnocení.

 SDM zavolá buď [EvaluateSync](../../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md) nebo [EvaluateAsync](../../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md) skutečně vyhodnotí výraz a hodnotu.

 V implementaci `IDebugExpressionContext2::ParseText`, DE používá modelu COM `CoCreateInstance` funkci pro vytvoření instance vyhodnocovače výrazů a získat [IDebugExpressionEvaluator](../../../extensibility/debugger/reference/idebugexpressionevaluator.md) rozhraní (podívejte se na příklad v `IDebugExpressionEvaluator` rozhraní). Pak zavolá DE [analyzovat](../../../extensibility/debugger/reference/idebugexpressionevaluator-parse.md) získat [IDebugParsedExpression](../../../extensibility/debugger/reference/idebugparsedexpression.md) rozhraní. Toto rozhraní se používá při provádění `IDebugExpression2::EvaluateSync` a `IDebugExpression2::EvaluateAsync` pro provedení vyhodnocení.

## <a name="requirements"></a>Požadavky
 Záhlaví: msdbg.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také:
- [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)
- [GetExpression](../../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2-getexpression.md)