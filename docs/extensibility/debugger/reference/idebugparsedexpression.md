---
title: IDebugParsedExpression | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugParsedExpression
helpviewer_keywords:
- IDebugParsedExpression interface
ms.assetid: be6486ed-b070-4898-95b1-58581bcb4447
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 22069b8eedb06d67eafaf7333f379a057c1b6f23
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "80725992"
---
# <a name="idebugparsedexpression"></a>IDebugParsedExpression
> [!IMPORTANT]
> V aplikaci Visual Studio 2015 je tento způsob implementace vyhodnocovacích vyhodnocení výrazů zastaralý. Informace o implementaci vyhodnocovacích vyhodnocení výrazů CLR naleznete v tématu [vyhodnocovací filtry výrazů CLR](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) a [Ukázka vyhodnocovacího filtru spravovaného výrazu](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).

 Toto rozhraní představuje analyzovaný výraz připravený k vyhodnocení.

## <a name="syntax"></a>Syntax

```
IDebugParsedExpression : IUnknown
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 Vyhodnocovací filtr výrazů implementuje toto rozhraní, aby představovalo analyzovaný výraz připravený k vyhodnocení.

## <a name="notes-for-callers"></a>Poznámky pro volající
 Volání metody [Parse](../../../extensibility/debugger/reference/idebugexpressionevaluator-parse.md) vrátí toto rozhraní.

## <a name="methods-in-vtable-order"></a>Metody v pořadí vtable
 Následující tabulka ukazuje metodu `IDebugParsedExpression` .

|Metoda|Popis|
|------------|-----------------|
|[EvaluateSync](../../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md)|Vyhodnotí analyzovaný výraz.|

## <a name="remarks"></a>Poznámky
 Pokud je volající připraven k vyhodnocení výrazu, volá [EvaluateSync](../../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md) k vrácení [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) , který obsahuje výsledek vyhodnocení. Tento postup dvou částí pro vyhodnocení, analýzu se pak vyhodnotí, umožňuje analyzovat výraz, který se vyhodnocuje víckrát, a obejít časově náročný proces analýzy výrazu.

## <a name="requirements"></a>Požadavky
 Záhlaví: ee. h

 Obor názvů: Microsoft. VisualStudio. Debugger. Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
- [Parse](../../../extensibility/debugger/reference/idebugexpressionevaluator-parse.md) (Parsování)
- [EvaluateSync](../../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md)
- [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)
