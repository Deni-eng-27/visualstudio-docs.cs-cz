---
title: Konstanty (přístup k rozhraní SDK ladění) | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- constants, DIA SDK
- DIA SDK, constants
ms.assetid: aca4ec77-bc08-4cdd-a6ce-8d4a28ea5ea3
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ed505499efcabd7173fea9d668cd9afa5ed6d925
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56608575"
---
# <a name="constants-debug-interface-access-sdk"></a>Konstanty (Přístup k rozhraní ladění SDK)
Tyto řetězcové konstanty lze použít k identifikaci různých oddílů sady soubor databáze (PDB) programu ladění prostřednictvím sady DIA SDK.

## <a name="constants"></a>Konstanty
Následující jsou deklarovány jako makra jazyka C/C++.

|– Makro|Hodnota|
|-----------|-----------|
|`DiaTable_Symbols`|L "Symboly"|
|`DiaTable_Sections`|L"Sections"|
|`DiaTable_SrcFiles`|L "SourceFiles"|
|`DiaTable_LineNums`|L"LineNumbers"|
|`DiaTable_SegMap`|L"SegmentMap"|
|`DiaTable_Dbg`|L"Dbg"|
|`DiaTable_InjSrc`|L "InjectedSource"|
|`DiaTable_FrameData`|L"FrameData"|

## <a name="example"></a>Příklad
Tady je příklad pomocí jedné z těchto symbolů:

```C++
HRESULT GetSymbolTable(IDiaEnumTables *pEnumTables, IDiaTable **pTable)
{
    HRESULT hr;
    VARIANT var;
    var.vt      = VT_BSTR;
    var.bstrVal = SysAllocString( DiaTable_Symbols );
    hr = pEnumTables->Item( var, pTable );
    return(hr);
}
```

## <a name="requirements"></a>Požadavky
Záhlaví: dia2.h

## <a name="see-also"></a>Viz také
- [Referenční informace](../../debugger/debug-interface-access/debug-interface-access-sdk-reference.md)
- [Výčty a struktury](../../debugger/debug-interface-access/enumerations-and-structures.md)
- [Rozhraní (Přístup k rozhraní ladění SDK)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)
- [IDiaEnumTables::Item](../../debugger/debug-interface-access/idiaenumtables-item.md)
