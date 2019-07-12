---
title: IDiaSymbol::get_unmodifiedType | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_unmodifiedType method
ms.assetid: bf914dc0-ff84-4f5d-9f75-1733b17f3be0
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 2e609f59e0d72628be4233be52738ff244c6acca
ms.sourcegitcommit: 75807551ea14c5a37aa07dd93a170b02fc67bc8c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/12/2019
ms.locfileid: "64806758"
---
# <a name="idiasymbolgetunmodifiedtype"></a>IDiaSymbol::get_unmodifiedType
Obnoví původní typ pro tento symbol. Použít, když [symtagenum – výčet](../../debugger/debug-interface-access/symtagenum.md) je nastavena na typu.

## <a name="syntax"></a>Syntaxe

```C++
HRESULT get_unmodifiedType( 
   IDiaSymbol** pRetVal
);
```

#### <a name="parameters"></a>Parametry
 `pRetVal`

[out] Vrátí [idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md) objekt, který představuje původní typ tento symbol.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí `S_FALSE` nebo kód chyby.

> [!NOTE]
> Vrácená hodnota `S_FALSE` znamená, že vlastnost není k dispozici pro symbol.

## <a name="remarks"></a>Poznámky
 Aktuální typ je úprava vrácené původního typu. Původní typ symbolu dá určit tak, že nejprve získat typ symbolu a potom dotazem, který vrátil typ pro původního typu. Všimněte si, že některé symboly nemusí mít upravený typ původního typu.

## <a name="requirements"></a>Požadavky
 Záhlaví: Dia2.h

 Knihovna: diaguids.lib

 DLL: msdia100.dll

## <a name="see-also"></a>Viz také
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)