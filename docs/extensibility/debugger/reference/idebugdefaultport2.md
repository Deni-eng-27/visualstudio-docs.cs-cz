---
title: IDebugDefaultPort2 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugDefaultPort2
helpviewer_keywords:
- IDebugDefaultPort2 interface
ms.assetid: 7b3452af-9a96-4c4c-9946-4339b72d3d7b
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: f560a3dabefb0a8dede6520dcd8fd47f609a7780
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "80732311"
---
# <a name="idebugdefaultport2"></a>IDebugDefaultPort2
Toto rozhraní poskytuje několik metod pro přístup k serveru a oznamovacímu zařízení portu.

## <a name="syntax"></a>Syntax

```
IDebugDefaultPort2 : IDebugPort2
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 Visual Studio implementuje toto rozhraní, aby představovalo port ladění pro přístup k programům. Vlastní dodavatel portu může implementovat toto rozhraní i v případě, že zpracovává vzdálené ladění.

## <a name="notes-for-callers"></a>Poznámky pro volající
 Argument metod v rozhraní [IDebugProgramProvider2](../../../extensibility/debugger/reference/idebugprogramprovider2.md) poskytuje toto rozhraní. Volání [QueryInterface](/cpp/atl/queryinterface) na rozhraní [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md) může také získat toto rozhraní.

## <a name="methods-in-vtable-order"></a>Metody v pořadí vtable
 Kromě metod definovaných v [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)toto rozhraní implementuje následující metody:

|Metoda|Popis|
|------------|-----------------|
|[GetPortNotify](../../../extensibility/debugger/reference/idebugdefaultport2-getportnotify.md)|Získá rozhraní oznámení portu z tohoto portu.|
|[GetServer](../../../extensibility/debugger/reference/idebugdefaultport2-getserver.md)|Získá rozhraní serveru, který je hostitelem tohoto portu.|
|[QueryIsLocal](../../../extensibility/debugger/reference/idebugdefaultport2-queryislocal.md)|Určuje, jestli je tento port na místním počítači spuštěný.|

## <a name="remarks"></a>Poznámky
 Název " `IDebugDefaultPort2` " je bitovou příponou misnomer, protože nepředstavuje výchozí port. Může se volat "IDebugPort3".

## <a name="requirements"></a>Požadavky
 Záhlaví: msdbg. h

 Obor názvů: Microsoft. VisualStudio. Debugger. Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
- [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)
- [IDebugProgramProvider2](../../../extensibility/debugger/reference/idebugprogramprovider2.md)
