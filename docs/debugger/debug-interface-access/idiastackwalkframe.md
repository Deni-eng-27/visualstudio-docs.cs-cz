---
title: Idiastackwalkframe – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
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
ms.openlocfilehash: 343c56e3d3175c26900b0cfb4cdc3d816a324404
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56630584"
---
# <a name="idiastackwalkframe"></a>IDiaStackWalkFrame
Zásobník kontextu mezi voláními udržuje [idiaframedata::Execute –](../../debugger/debug-interface-access/idiaframedata-execute.md) metody.

## <a name="syntax"></a>Syntaxe

```
IDiaStackWalkFrame : IUnknown
```

## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí
 V následující tabulce jsou uvedeny metody objektu `IDiaStackWalkFrame`.

|Metoda|Popis|
|------------|-----------------|
|[IDiaStackWalkFrame::get_registerValue](../../debugger/debug-interface-access/idiastackwalkframe-get-registervalue.md)|Načte hodnotu registru.|
|[IDiaStackWalkFrame::put_registerValue](../../debugger/debug-interface-access/idiastackwalkframe-put-registervalue.md)|Nastaví hodnotu registru.|
|[IDiaStackWalkFrame::readMemory](../../debugger/debug-interface-access/idiastackwalkframe-readmemory.md)|Přečte paměti z image.|
|[IDiaStackWalkFrame::searchForReturnAddress](../../debugger/debug-interface-access/idiastackwalkframe-searchforreturnaddress.md)|Vyhledá zadaný zásobník snímků pro nejbližší zpáteční adresu funkce.|
|[IDiaStackWalkFrame::searchForReturnAddressStart](../../debugger/debug-interface-access/idiastackwalkframe-searchforreturnaddressstart.md)|Vyhledá zadaný zásobník snímků pro zpáteční adresu na nebo blízko ní zadané adrese.|

## <a name="remarks"></a>Poznámky
 Toto rozhraní se používá při provádění programu pro čtení a zápis registry také přístup k paměti a najít návratový adresy.

## <a name="notes-for-callers"></a>Poznámky pro volající
 Klientská aplikace implementuje toto rozhraní a předá instance rozhraní [idiaframedata::Execute –](../../debugger/debug-interface-access/idiaframedata-execute.md) metody. Stejnou instanci toto rozhraní je používán znovu a znovu pro zachování stavu registrů při každé vyvolání sady `execute` metody. `execute` Metody tohoto rozhraní používá rovněž k určení zpáteční adresu.

## <a name="requirements"></a>Požadavky
 Záhlaví: Dia2.h

 Knihovna: diaguids.lib

 DLL: msdia80.dll

## <a name="see-also"></a>Viz také
- [Rozhraní (Přístup k rozhraní ladění SDK)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)
- [IDiaFrameData::execute](../../debugger/debug-interface-access/idiaframedata-execute.md)