---
title: IDebugDisassemblyStream2 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugDisassemblyStream2
helpviewer_keywords:
- IDebugDisassemblyStream2 interface
ms.assetid: b03cab0c-3f0b-4cc6-88dc-acb3b48c567a
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 98ba08e4ec32aceaf6c265714848939cc6ad9c66
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "80732042"
---
# <a name="idebugdisassemblystream2"></a>IDebugDisassemblyStream2
Toto rozhraní představuje datový proud instrukcí.

## <a name="syntax"></a>Syntax

```
IDebugDisassemblyStream2 : IUnknown
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 Ladicí stroj implementuje toto rozhraní pro podporu zpětného překladu kódu programu.

## <a name="notes-for-callers"></a>Poznámky pro volající
 Volání metody [GetDisassemblyStream](../../../extensibility/debugger/reference/idebugprogram2-getdisassemblystream.md) vrací toto rozhraní.

## <a name="methods-in-vtable-order"></a>Metody v pořadí vtable
 V následující tabulce jsou uvedeny metody `IDebugDisassemblyStream2` .

|Metoda|Popis|
|------------|-----------------|
|[Číst](../../../extensibility/debugger/reference/idebugdisassemblystream2-read.md)|Přečte pokyny od aktuální pozice v datovém proudu zpětného překladu.|
|[Seek](../../../extensibility/debugger/reference/idebugdisassemblystream2-seek.md)|Přesune ukazatel na čtení ve streamu zpětného překladu a určí stanovený počet instrukcí vzhledem k zadané pozici.|
|[GetCodeLocationId](../../../extensibility/debugger/reference/idebugdisassemblystream2-getcodelocationid.md)|Vrátí identifikátor umístění kódu pro konkrétní kontext kódu.|
|[GetCodeContext](../../../extensibility/debugger/reference/idebugdisassemblystream2-getcodecontext.md)|Vrátí objekt kontextu kódu odpovídající zadanému identifikátoru umístění kódu.|
|[GetCurrentLocation](../../../extensibility/debugger/reference/idebugdisassemblystream2-getcurrentlocation.md)|Vrátí identifikátor umístění kódu, který představuje aktuální umístění kódu.|
|[GetDocument](../../../extensibility/debugger/reference/idebugdisassemblystream2-getdocument.md)|Načte zdrojový dokument přidružený k tomuto datovému proudu zpětného překladu.|
|[GetScope](../../../extensibility/debugger/reference/idebugdisassemblystream2-getscope.md)|Získá rozsah tohoto streamu zpětného překladu.|
|[GetSize](../../../extensibility/debugger/reference/idebugdisassemblystream2-getsize.md)|Získá velikost tohoto streamu zpětného překladu.|

## <a name="remarks"></a>Poznámky
 Stream zpětného překladu se dá vytvořit tak, aby představoval celý adresní prostor, nebo jenom funkci nebo modul v rámci prostoru. Jednotlivé instrukce jsou reprezentovány strukturou [DisassemblyData](../../../extensibility/debugger/reference/disassemblydata.md) vrácenou voláním metody [Read](../../../extensibility/debugger/reference/idebugdisassemblystream2-read.md) .

## <a name="requirements"></a>Požadavky
 Záhlaví: msdbg. h

 Obor názvů: Microsoft. VisualStudio. Debugger. Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
- [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)
- [GetDisassemblyStream](../../../extensibility/debugger/reference/idebugprogram2-getdisassemblystream.md)
- [DisassemblyData](../../../extensibility/debugger/reference/disassemblydata.md)
