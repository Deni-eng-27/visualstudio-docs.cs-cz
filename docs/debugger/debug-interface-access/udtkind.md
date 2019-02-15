---
title: Udtkind – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- UdtKind enumeration
ms.assetid: 400b59b9-373c-42cb-aae1-570494214328
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: bb649915179bc6e6b767970150df99caff306b4c
ms.sourcegitcommit: 752f03977f45169585e407ef719450dbe219b7fc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/15/2019
ms.locfileid: "56317728"
---
# <a name="udtkind"></a>UdtKind
Popisuje různé uživatelem definovaný typ (UDT).

## <a name="syntax"></a>Syntaxe

```C++
enum UdtKind {
    UdtStruct,
    UdtClass,
    UdtUnion,
    UdtInterface
};
```

## <a name="elements"></a>Elementy
UdtStruct  
UDT je struktura.

UdtClass  
UDT je třída.

UdtUnion  
UDT je sjednocení.

UdtInterface  
UDT je rozhraní.

## <a name="remarks"></a>Poznámky
Jsou vrácené hodnoty v tento výčet [idiasymbol::get_udtkind –](../../debugger/debug-interface-access/idiasymbol-get-udtkind.md) metody.

## <a name="requirements"></a>Požadavky
Záhlaví: cvconst.h

## <a name="see-also"></a>Viz také
[Výčty a struktury](../../debugger/debug-interface-access/enumerations-and-structures.md)  
[IDiaSymbol::get_udtKind](../../debugger/debug-interface-access/idiasymbol-get-udtkind.md)
