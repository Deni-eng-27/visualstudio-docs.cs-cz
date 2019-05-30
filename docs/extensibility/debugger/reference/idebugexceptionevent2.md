---
title: IDebugExceptionEvent2 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugExceptionEvent2
helpviewer_keywords:
- IDebugExceptionEvent2 interface
ms.assetid: 53d32e59-a84b-4710-833e-c5ab08100516
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 3fd2a449c71b69c654cd19846990f7b722f706de
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66325982"
---
# <a name="idebugexceptionevent2"></a>IDebugExceptionEvent2
Ladicí stroj (DE) pošle toto rozhraní Správce ladění relace (SDM), když je vyvolána výjimka při provádění programu.

## <a name="syntax"></a>Syntaxe

```
IDebugExceptionEvent2 : IUnknown
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 DE implementuje toto rozhraní k sestavě, že v programu, který se právě ladí došlo k výjimce. [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) na stejný objekt jako toto rozhraní musí implementovat rozhraní. Používá SDM [QueryInterface](/cpp/atl/queryinterface) přístup `IDebugEvent2` rozhraní.

## <a name="notes-for-callers"></a>Poznámky pro volající
 DE vytvoří a odešle tento objekt události nahlásit výjimku. Událost je odeslána pomocí [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) funkce zpětného volání, který poskytl SDM při připojení k laděnému programu.

## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí
 V následující tabulce jsou uvedeny metody objektu `IDebugExceptionEvent2`.

|Metoda|Popis|
|------------|-----------------|
|[GetException](../../../extensibility/debugger/reference/idebugexceptionevent2-getexception.md)|Získá podrobné informace o výjimce, která vyvolala Tato událost.|
|[GetExceptionDescription](../../../extensibility/debugger/reference/idebugexceptionevent2-getexceptiondescription.md)|Získá čitelný popis výjimky vyvolána, který aktivuje tuto událost.|
|[CanPassToDebuggee](../../../extensibility/debugger/reference/idebugexceptionevent2-canpasstodebuggee.md)|Určuje, zda ladicí stroj (DE) podporuje možnost k laděnému při provádění pokračuje programu předat tuto výjimku.|
|[PassToDebuggee](../../../extensibility/debugger/reference/idebugexceptionevent2-passtodebuggee.md)|Určuje, zda výjimky by měly být předány program laděn při provádění pokračuje, nebo pokud by měl být zahozeny výjimku.|

## <a name="requirements"></a>Požadavky
 Záhlaví: msdbg.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="remarks"></a>Poznámky
 Před odesláním události, DE zkontroluje, pokud tato událost výjimky určenou výjimka první příležitosti nebo druhém předchozí volání [SetException](../../../extensibility/debugger/reference/idebugengine2-setexception.md). Pokud je určený jako první odpovídající výjimce `IDebugExceptionEvent2` událost je odeslána do SDM. V opačném případě je DE poskytuje aplikaci příležitost dobře se zpracovat výjimku. Není-li zadána žádná obslužná rutina výjimky a výjimky je určený jako sekundu odpovídající výjimce, `IDebugExceptionEvent2` událost je odeslána do SDM. V opačném případě je DE pokračuje v provádění programu a operačního systému nebo modul runtime zpracovává výjimku.

## <a name="see-also"></a>Viz také:
- [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)
- [SetException](../../../extensibility/debugger/reference/idebugengine2-setexception.md)
- [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)
- [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)