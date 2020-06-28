---
title: 'IDiaSession:: findChildren – | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::findChildren method
ms.assetid: 5d19046f-f668-4aa9-8788-95cda9a98997
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: dcc62ed0b4a1f0a9ddd43ef692f748db4d9b6f10
ms.sourcegitcommit: 66f31cc4ce1236e638ab58d2f70d3646206386fa
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/27/2020
ms.locfileid: "85465837"
---
# <a name="idiasessionfindchildren"></a>IDiaSession::findChildren
Načte všechny podřízené položky zadaného nadřazeného identifikátoru, který se shoduje s názvem a typem symbolu.

## <a name="syntax"></a>Syntaxe

```C++
HRESULT findChildren ( 
   IDiaSymbol*       parent,
   SymTagEnum        symtag,
   LPCOLESTR         name,
   DWORD             compareFlags,
   IDiaEnumSymbols** ppResult
);
```

#### <a name="parameters"></a>Parametry
 `parent`

pro Objekt [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md) představující nadřazený prvek. Pokud je tento nadřazený symbol funkce, modul nebo blok, pak jsou jeho Lexikální podřízené prvky vráceny v `ppResult` . Pokud je nadřazený symbol typu, pak jsou vráceny podřízené třídy. Pokud je tento parametr `NULL` , `symtag` musí být nastaven na `SymTagExe` nebo `SymTagNull` , což vrátí globální obor (soubor. exe).

 `symtag`

pro Určuje značku symbolu podřízených objektů, které mají být načteny. Hodnoty jsou pořízeny výčtem [výčtu SymTagEnum –](../../debugger/debug-interface-access/symtagenum.md) . Nastavte na `SymTagNull` načtení všech podřízených objektů.

 `name`

pro Určuje název podřízených objektů, které mají být načteny. Nastavte na hodnotu `NULL` pro všechny podřízené položky, které mají být načteny.

 `compareFlags`

pro Určuje možnosti porovnání použité pro porovnávání názvů. Hodnoty výčtového výčtu [namesearchoptions –](../../debugger/debug-interface-access/namesearchoptions.md) lze použít samostatně nebo v kombinaci.

 `ppResult`

mimo Vrátí objekt [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md) , který obsahuje seznam načtených podřízených symbolů.

## <a name="return-value"></a>Návratová hodnota
 V případě úspěchu vrátí. `S_OK` jinak vrátí kód chyby.

## <a name="example"></a>Příklad
 Následující příklad ukazuje, jak najít místní proměnné funkce `pFunc` , které odpovídají názvu `szVarName` .

```C++
IDiaEnumSymbols* pEnum;
pSession->findChildren( pFunc, SymTagData, szVarName, nsCaseSensitive, &pEnum );
```

## <a name="see-also"></a>Viz také
- [Přehled](../../debugger/debug-interface-access/overview-debug-interface-access-sdk.md)
- [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)
- [IDiaSession](../../debugger/debug-interface-access/idiasession.md)
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
- [NameSearchOptions – výčet](../../debugger/debug-interface-access/namesearchoptions.md)
- [SymTagEnum – výčet](../../debugger/debug-interface-access/symtagenum.md)