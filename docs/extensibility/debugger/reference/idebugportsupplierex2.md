---
title: IDebugPortSupplierEx2 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugPortSupplierEx2 interface
ms.assetid: dae0050a-a50a-4f35-bfbd-e538f537b20f
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 26387618b320ed56ce754e64698fbb1c4223f2f6
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "80724322"
---
# <a name="idebugportsupplierex2"></a>IDebugPortSupplierEx2
Poskytuje podporu pro dodavatele portu pro výběr a interakci se základním serverem.

## <a name="syntax"></a>Syntax

```
IDebugPortSupplierEx2 : IUnknown
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 Vlastní dodavatel portu implementuje toto rozhraní, aby mohl vybrat základní server, který se má použít.

## <a name="methods"></a>Metody
 V následující tabulce jsou uvedeny metody **IDebugPortSupplierEx2**.

|Metoda|Popis|
|------------|-----------------|
|[SetServer](../../../extensibility/debugger/reference/idebugportsupplierex2-setserver.md)|Nastaví základní server pro dodavatele portu.|

## <a name="requirements"></a>Požadavky
 Záhlaví: Portpriv. h

 Obor názvů: Microsoft. VisualStudio. Debugger. Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
- [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)
- [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md)
- [IDebugPortSupplier3](../../../extensibility/debugger/reference/idebugportsupplier3.md)
