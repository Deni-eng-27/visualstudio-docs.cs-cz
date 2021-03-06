---
title: IDebugProviderProgramNode2 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProviderProgramNode2
helpviewer_keywords:
- IDebugProviderProgramNode2
ms.assetid: f0bca1cc-afbe-44cf-b5aa-d078aa685d24
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 815a945f6fb591960ebf0bf4b4fcd9d842ffefd3
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "80720679"
---
# <a name="idebugproviderprogramnode2"></a>IDebugProviderProgramNode2
Toto rozhraní zařazování rozhraní souvisejících s programy napříč hranicemi procesů.

## <a name="syntax"></a>Syntax

```
IDebugProviderProgramNode2 : IUnknown
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 Ladicí stroj (DE) implementuje toto rozhraní na stejném objektu, který implementuje [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md) pro podporu zařazování rozhraní napříč hranicemi procesů.

## <a name="notes-for-callers"></a>Poznámky pro volající
 [QueryInterface](/cpp/atl/queryinterface) `IDebugProgramNode2` Chcete-li získat toto rozhraní, zavolejte na rozhraní QueryInterface. Pokud toto rozhraní nelze získat, DE nepodporuje zařazování rozhraní.

## <a name="methods-in-vtable-order"></a>Metody v pořadí vtable
 Toto rozhraní implementuje následující metodu:

|Metoda|Popis|
|------------|-----------------|
|[UnmarshalDebuggeeInterface](../../../extensibility/debugger/reference/idebugproviderprogramnode2-unmarshaldebuggeeinterface.md)|Získá zadané rozhraní napříč hranicemi procesu.|

## <a name="remarks"></a>Poznámky
 Toto rozhraní je implementováno, když je DE spuštěna v odděleném prostoru procesu z laděného programu: například při spuštění DE v prostoru procesu sady Visual Studio namísto procesu ladění programu.

## <a name="requirements"></a>Požadavky
 Záhlaví: msdbg. h

 Obor názvů: Microsoft. VisualStudio. Debugger. Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
- [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)
- [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)
