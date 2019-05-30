---
title: IDebugManagedObject | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugManagedObject
helpviewer_keywords:
- IDebugManagedObject interface
ms.assetid: 3ae09d34-112c-4285-80ee-9f7f8dc414d7
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 6744ae98a0210a6832bce1bdb0cd68f08145f3eb
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66349417"
---
# <a name="idebugmanagedobject"></a>IDebugManagedObject
> [!IMPORTANT]
> V sadě Visual Studio 2015 je zastaralý tímto způsobem implementace vyhodnocovače výrazů. Informace o implementace vyhodnocovače výrazů modulu CLR najdete v tématu [vyhodnocovače výrazů modulu CLR](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) a [spravované ukázka Chyba při vyhodnocování výrazu](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).

 Toto rozhraní umožňuje vyhodnocovací filtr výrazů (EE) pro volání vlastnosti nebo metody na instance třídy hodnotu (například `System.Decimal`) a nastavení jejich hodnoty bez volání [vyhodnotit](../../../extensibility/debugger/reference/idebugfunctionobject-evaluate.md) na program, který se právě ladí.

## <a name="syntax"></a>Syntaxe

```
IDebugManagedObject : IDebugObject
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 Vyhodnocovače výrazů implementuje toto rozhraní k reprezentaci objektu spravovaného kódu, například proměnná.

## <a name="notes-for-callers"></a>Poznámky pro volající
 Chcete-li získat toto rozhraní, zavolejte [GetManagedDebugObject](../../../extensibility/debugger/reference/idebugobject-getmanageddebugobject.md) na [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) , která představuje instance třídy value class.

## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí
 Kromě metod zděděných z [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md), `IDebugManagedObject` rozhraní poskytuje následující metody.

|Metoda|Popis|
|------------|-----------------|
|[GetManagedObject](../../../extensibility/debugger/reference/idebugmanagedobject-getmanagedobject.md)|Vrátí rozhraní, který představuje objekt spravovaný kód a ze kterých žádné odpovídající spravovaného kódu můžete získat rozhraní.|
|[SetFromManagedObject](../../../extensibility/debugger/reference/idebugmanagedobject-setfrommanagedobject.md)|Nastaví hodnotu tohoto objektu na hodnotu objektu zadaný spravovaný kód.|

## <a name="remarks"></a>Poznámky
 Vyhodnocovače výrazů toto rozhraní využívá k ukládání objektu spravovaného kódu v strom analýzy.

## <a name="requirements"></a>Požadavky
 Záhlaví: ee.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také:
- [Rozhraní pro vyhodnocení výrazu](../../../extensibility/debugger/reference/expression-evaluation-interfaces.md)
- [Evaluate](../../../extensibility/debugger/reference/idebugfunctionobject-evaluate.md)