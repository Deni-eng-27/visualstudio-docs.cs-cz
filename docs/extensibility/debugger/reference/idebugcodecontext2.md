---
title: IDebugCodeContext2 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugCodeContext2
helpviewer_keywords:
- IDebugCodeContext2 interface
ms.assetid: 3670439e-2171-405d-9d77-dedb0f1cba93
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 4e15692a94e3f1c80d6bd6f12ecb0c2ce7271c8d
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62876761"
---
# <a name="idebugcodecontext2"></a>IDebugCodeContext2
Toto rozhraní představuje počáteční pozici kódu instrukce. Pro většinu za běhu architektury v současné době kontext kódu můžete představit jako adresa ve službě stream provádění programu.

## <a name="syntax"></a>Syntaxe

```
IDebugCodeContext2 : IDebugMemoryContext2
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 Ladicí stroj implementuje toto rozhraní k propojení kódu instrukce k umístění dokumentu.

## <a name="notes-for-callers"></a>Poznámky pro volající
 Metody na mnoho rozhraní nejvíce obvykle vrací toto rozhraní [GetCodeContext](../../../extensibility/debugger/reference/idebugstackframe2-getcodecontext.md). Používá se také často s [IDebugDisassemblyStream2](../../../extensibility/debugger/reference/idebugdisassemblystream2.md) rozhraní také informace o řešení zarážek.

## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí
 Kromě metod na [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md) rozhraní, toto rozhraní implementuje následujících metod:

|Metoda|Popis|
|------------|-----------------|
|[GetDocumentContext](../../../extensibility/debugger/reference/idebugcodecontext2-getdocumentcontext.md)|Získá kontext dokumentu, který odpovídá kontext active kódu.|
|[GetLanguageInfo](../../../extensibility/debugger/reference/idebugcodecontext2-getlanguageinfo.md)|Získá informace o jazyce pro tento kontext kódu.|

## <a name="remarks"></a>Poznámky
 Klíčovým rozdílem mezi `IDebugCodeContext2` rozhraní a [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md) rozhraní je, že `IDebugCodeContext2` je vždy instrukce zarovnání. To znamená, že `IDebugCodeContext2` vždy odkazuje na začátku instrukce, že `IDebugMemoryContext2` může odkazovat na všechny bajty paměti v architektuře za běhu. `IDebugCodeContext2` se zvýší, podle pokynů, nikoli podle velikosti storage úrovně basic (obvykle bajtů).

## <a name="requirements"></a>Požadavky
 Záhlaví: msdbg.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
- [GetDisassemblyStream](../../../extensibility/debugger/reference/idebugprogram2-getdisassemblystream.md)
- [CanSetNextStatement](../../../extensibility/debugger/reference/idebugthread2-cansetnextstatement.md)
- [SetNextStatement](../../../extensibility/debugger/reference/idebugthread2-setnextstatement.md)
- [GetCodeContext](../../../extensibility/debugger/reference/idebugcanstopevent2-getcodecontext.md)
- [GetCodeContext](../../../extensibility/debugger/reference/idebugstackframe2-getcodecontext.md)
- [Next](../../../extensibility/debugger/reference/ienumdebugcodecontexts2-next.md)
- [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)