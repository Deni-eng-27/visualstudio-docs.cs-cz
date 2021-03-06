---
title: IDebugProgramCreateEvent2 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProgramCreateEvent2
helpviewer_keywords:
- IDebugProgramCreateEvent2 interface
ms.assetid: b19a7934-6179-4a68-9075-bd7dcd640b05
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 78088d6e5da61c32302c13b08143c9ed902452e2
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "80722625"
---
# <a name="idebugprogramcreateevent2"></a>IDebugProgramCreateEvent2
Toto rozhraní je odesláno ladicím modulem (DE) do nástroje Session Debug Manager (SDM), když je program připojen k.

## <a name="syntax"></a>Syntax

```
IDebugProgramCreateEvent2 : IUnknown
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 DE nebo vlastní dodavatel portu implementuje toto rozhraní, aby nahlásilo, že byl vytvořen program, obvykle v okamžiku, kdy je program připojen k. Rozhraní [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) musí být implementováno na stejném objektu jako toto rozhraní. Model SDM používá `QueryInterface` metodu pro přístup k `IDebugEvent2` rozhraní.

## <a name="notes-for-callers"></a>Poznámky pro volající
 Dodavatel DE nebo vlastní port vytvoří a odešle tento objekt události, aby nahlásil vytváření programu. DE pošle tuto událost pomocí funkce zpětného volání [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) , která je dodána serverem SDM, když je připojen k laděnému programu. Vlastní dodavatel portu odešle tuto událost pomocí rozhraní [IDebugPortEvents2](../../../extensibility/debugger/reference/idebugportevents2.md) .

## <a name="remarks"></a>Poznámky
 Dodavatel DE nebo vlastního portu publikuje nové rozhraní [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md) voláním [PublishProgramNode](../../../extensibility/debugger/reference/idebugprogrampublisher2-publishprogramnode.md).

## <a name="requirements"></a>Požadavky
 Záhlaví: msdbg. h

 Obor názvů: Microsoft. VisualStudio. Debugger. Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
- [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)
- [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)
- [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)
- [IDebugPortEvents2](../../../extensibility/debugger/reference/idebugportevents2.md)
- [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)
