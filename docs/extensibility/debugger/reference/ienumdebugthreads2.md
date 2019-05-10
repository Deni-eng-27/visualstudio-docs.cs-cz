---
title: IEnumDebugThreads2 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumDebugThreads2
helpviewer_keywords:
- IEnumDebugThreads2
ms.assetid: 1854f078-3b49-42c2-b65b-33e3b506fd63
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 76a7267690f359d960a0c5e9b6f6a1c502d5d4f1
ms.sourcegitcommit: 50f0c3f2763a05de8482b3579026d9c76c0e226c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/09/2019
ms.locfileid: "65461180"
---
# <a name="ienumdebugthreads2"></a>IEnumDebugThreads2
Toto rozhraní zobrazí vlákna spuštěná během aktuální relace ladění.

## <a name="syntax"></a>Syntaxe

```
IEnumDebugThreads2 : IUnknown
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 Ladicí stroj (DE) implementuje toto rozhraní představující seznam vláken v programu.

## <a name="notes-for-callers"></a>Poznámky pro volající
 Volání [enumthreads –](../../../extensibility/debugger/reference/idebugprocess2-enumthreads.md) získat toto rozhraní představující seznam všechna vlákna ve všech aplikacích spuštěných v procesu. Volání [enumthreads –](../../../extensibility/debugger/reference/idebugprogram2-enumthreads.md) získat toto rozhraní představující seznam vlákna spuštěná v programu.

## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí
 V následující tabulce jsou uvedeny metody objektu `IEnumDebugThreads2`.

|Metoda|Popis|
|------------|-----------------|
|[Next](../../../extensibility/debugger/reference/ienumdebugthreads2-next.md)|Načte zadaný počet vláken v pořadí výčtu.|
|[Skip](../../../extensibility/debugger/reference/ienumdebugthreads2-skip.md)|Vynechá zadaný počet vláken v sekvenci výčtu.|
|[Reset](../../../extensibility/debugger/reference/ienumdebugthreads2-reset.md)|Návrat na začátek sekvence výčtu.|
|[Clone](../../../extensibility/debugger/reference/ienumdebugthreads2-clone.md)|Vytvoří čítač, který obsahuje stejné stav výčtu, jako je aktuální.|
|[GetCount](../../../extensibility/debugger/reference/ienumdebugthreads2-getcount.md)|Získá počet vláken v enumerátor.|

## <a name="remarks"></a>Poznámky
 Visual Studio obvykle obdrží toto rozhraní se aktualizovat **vlákna** okno stejně jako získat první vlákno seznamu, aby bylo možné volat [Execute](../../../extensibility/debugger/reference/idebugprocess3-execute.md), [pokračovat](../../../extensibility/debugger/reference/idebugprocess3-continue.md), a [Krok](../../../extensibility/debugger/reference/idebugprocess3-step.md).

## <a name="requirements"></a>Požadavky
 Záhlaví: msdbg.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také:
- [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)
- [EnumThreads](../../../extensibility/debugger/reference/idebugprocess2-enumthreads.md)
- [EnumThreads](../../../extensibility/debugger/reference/idebugprogram2-enumthreads.md)
- [Step](../../../extensibility/debugger/reference/idebugprocess3-step.md)
- [Continue](../../../extensibility/debugger/reference/idebugprocess3-continue.md)
- [Execute](../../../extensibility/debugger/reference/idebugprocess3-execute.md)
