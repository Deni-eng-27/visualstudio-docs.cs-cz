---
title: IDebugManagedObject | Dokumenty společnosti Microsoft
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugManagedObject
helpviewer_keywords:
- IDebugManagedObject interface
ms.assetid: 3ae09d34-112c-4285-80ee-9f7f8dc414d7
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 6fbd270aa1b65f05f308d41d22f154fb53b8833d
ms.sourcegitcommit: 16a4a5da4a4fd795b46a0869ca2152f2d36e6db2
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/06/2020
ms.locfileid: "80727688"
---
# <a name="idebugmanagedobject"></a>IDebugManagedObject
> [!IMPORTANT]
> V sadě Visual Studio 2015 tento způsob implementace vyhodnocení výrazů je zastaralé. Informace o implementaci vyhodnocení exprese CLR naleznete v tématu [Vyhodnocení exprese CLR](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) a [ukázka vyhodnocení spravovaného výrazu](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).

 Toto rozhraní umožňuje vyhodnocení výrazu (EE) volat vlastnosti nebo metody `System.Decimal`na instance třídy hodnoty (například) a nastavit jejich hodnotu bez volání [Vyhodnotit](../../../extensibility/debugger/reference/idebugfunctionobject-evaluate.md) na program, který je laděn.

## <a name="syntax"></a>Syntaxe

```
IDebugManagedObject : IDebugObject
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 Vyhodnocení výrazu implementuje toto rozhraní reprezentovat objekt spravovaného kódu, jako je například proměnná.

## <a name="notes-for-callers"></a>Poznámky pro volající
 Chcete-li získat toto rozhraní, volejte [GetManagedDebugObject](../../../extensibility/debugger/reference/idebugobject-getmanageddebugobject.md) na [IDebugObject,](../../../extensibility/debugger/reference/idebugobject.md) který představuje instanci třídy value.

## <a name="methods-in-vtable-order"></a>Metody v pořadí Vtable
 Kromě metod zděděných z [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)rozhraní `IDebugManagedObject` zveřejňuje následující metody.

|Metoda|Popis|
|------------|-----------------|
|[GetManagedObject](../../../extensibility/debugger/reference/idebugmanagedobject-getmanagedobject.md)|Vrátí rozhraní, které představuje objekt spravovaného kódu a ze kterého lze získat jakékoli příslušné rozhraní spravovaného kódu.|
|[SetFromManagedObject](../../../extensibility/debugger/reference/idebugmanagedobject-setfrommanagedobject.md)|Nastaví hodnotu tohoto objektu na hodnotu zadaného objektu spravovaného kódu.|

## <a name="remarks"></a>Poznámky
 Vyhodnocení výrazu používá toto rozhraní k uložení objektu spravovaného kódu ve stromu analýzy.

## <a name="requirements"></a>Požadavky
 Záhlaví: ee.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
- [Rozhraní pro vyhodnocení výrazu](../../../extensibility/debugger/reference/expression-evaluation-interfaces.md)
- [Vyhodnotit](../../../extensibility/debugger/reference/idebugfunctionobject-evaluate.md)
