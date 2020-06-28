---
title: IDiaStackWalkFrame | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackWalkFrame interface
ms.assetid: 42d82845-d6f6-4846-9ecd-9dd169216077
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ee80b9bbb6d16f2aa4264491593d1864bdade690
ms.sourcegitcommit: 66f31cc4ce1236e638ab58d2f70d3646206386fa
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/27/2020
ms.locfileid: "85464805"
---
# <a name="idiastackwalkframe"></a>IDiaStackWalkFrame
Udržuje kontext zásobníku mezi voláními metody [IDiaFrameData:: Execute](../../debugger/debug-interface-access/idiaframedata-execute.md) .

## <a name="syntax"></a>Syntax

```
IDiaStackWalkFrame : IUnknown
```

## <a name="methods-in-vtable-order"></a>Metody v pořadí vtable
 V následující tabulce jsou uvedeny metody `IDiaStackWalkFrame` .

|Metoda|Popis|
|------------|-----------------|
|[IDiaStackWalkFrame::get_registerValue](../../debugger/debug-interface-access/idiastackwalkframe-get-registervalue.md)|Načte hodnotu registru.|
|[IDiaStackWalkFrame::put_registerValue](../../debugger/debug-interface-access/idiastackwalkframe-put-registervalue.md)|Nastaví hodnotu registru.|
|[IDiaStackWalkFrame::readMemory](../../debugger/debug-interface-access/idiastackwalkframe-readmemory.md)|Načte paměť z image.|
|[IDiaStackWalkFrame::searchForReturnAddress](../../debugger/debug-interface-access/idiastackwalkframe-searchforreturnaddress.md)|Vyhledá zadaný rámec zásobníku pro nejbližší návratovou adresu funkce.|
|[IDiaStackWalkFrame::searchForReturnAddressStart](../../debugger/debug-interface-access/idiastackwalkframe-searchforreturnaddressstart.md)|Vyhledá zadaný rámec zásobníku pro zpáteční adresu na zadané adrese nebo na ní.|

## <a name="remarks"></a>Poznámky
 Toto rozhraní se používá při provádění programu ke čtení a zápisu registrů a také k přístupu do paměti a k nalezení návratových adres.

## <a name="notes-for-callers"></a>Poznámky pro volající
 Klientská aplikace implementuje toto rozhraní a předá instanci rozhraní metodě [IDiaFrameData:: Execute](../../debugger/debug-interface-access/idiaframedata-execute.md) . Stejná instance tohoto rozhraní se znovu použije a znovu zachová stav registrů během každého vyvolání `execute` metody. `execute`Metoda také používá toto rozhraní k určení zpáteční adresy.

## <a name="requirements"></a>Požadavky
 Záhlaví: Dia2. h

 Knihovna: diaguids. lib

 KNIHOVNA DLL: msdia80.dll

## <a name="see-also"></a>Viz také
- [Rozhraní (Přístup k rozhraní ladění SDK)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)
- [IDiaFrameData::execute](../../debugger/debug-interface-access/idiaframedata-execute.md)