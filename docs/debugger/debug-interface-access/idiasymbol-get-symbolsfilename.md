---
title: Idiasymbol::get_symbolsfilename – | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_symbolsFileName method
ms.assetid: c1aa39ee-d645-431e-bf5f-0640c0998934
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b74246eac5d47f4c73df787e51d89863a526ef4d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idiasymbolgetsymbolsfilename"></a>IDiaSymbol::get_symbolsFileName
Načte název souboru, ze které byla načtena symboly.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT get_symbolsFileName (   
   BSTR* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pRetVal`  
 [out] Vrátí název souboru, ze které byla načtena symboly.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí `S_FALSE` nebo chybový kód.  
  
> [!NOTE]
>  Vrácená hodnota `S_FALSE` znamená vlastnost není k dispozici pro symbol.  
  
## <a name="remarks"></a>Poznámky  
 Tato vlastnost je platná pouze pro symboly s [SymTagEnum – výčet](../../debugger/debug-interface-access/symtagenum.md) hodnotu `SymTagExe` zároveň mají globální rozsah.  
  
## <a name="see-also"></a>Viz také  
 [Idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md)   
 [SymTagEnum – výčet](../../debugger/debug-interface-access/symtagenum.md)