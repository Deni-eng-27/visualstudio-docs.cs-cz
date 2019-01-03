---
title: IDiaSymbol::findChildrenExByRVA | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::findChildrenExByRVA
ms.assetid: cbc57c6c-7d64-4469-a114-1dd6671e5ec5
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 83711ca61a1bd9a27a7ebed2262bd5ca3f3487e1
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53903062"
---
# <a name="idiasymbolfindchildrenexbyrva"></a>IDiaSymbol::findChildrenExByRVA
Načte podřízené objekty daného symbolu, které jsou platné na zadaný relativní virtuální adrese (RVA).  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT findChildrenExByRVA (   
   enum SymTagEnum   symtag,  
   LPCOLESTR         name,  
   DWORD             compareFlags,  
   DWORD             address,  
   IDiaEnumSymbols** ppResult  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `symtag`  
 [in] Určuje symbol značky podřízené položky, které se mají načíst, jak jsou definovány v [symtagenum – výčet](../../debugger/debug-interface-access/symtagenum.md). Nastavte na `SymTagNull` pro všechny podřízené objekty, které se mají načíst.  
  
 `name`  
 [in] Určuje název podřízenou položku, která se má načíst. Nastavte na `NULL` pro všechny podřízené objekty, které se mají načíst.  
  
 `compareFlags`  
 [in] Určení možností porovnání uplatňovat na odpovídající název. Hodnoty z [namesearchoptions – výčet](../../debugger/debug-interface-access/namesearchoptions.md) výčtu lze použít samostatně nebo v kombinaci.  
  
 `address`  
 [in] Určuje, adresa RVA.  
  
 `ppResult`  
 [out] Vrátí [idiaenumsymbols –](../../debugger/debug-interface-access/idiaenumsymbols.md) načíst objekt, který obsahuje seznam podřízenými symboly.  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrátí `S_OK` Pokud byl nalezen nejméně jeden podřízený prvek symbolu nebo vrátí `S_FALSE` Pokud nebyly nalezeny žádné podřízené položky; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Lokální symboly, které jsou vráceny zahrnovat informace o rozsahu za provozu.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: dia2.h  
  
 Knihovna: diaguids.lib  
  
 Knihovny DLL: msdia100.dll  
  
## <a name="see-also"></a>Viz také  
 [Idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md)   
 [Symtagenum – výčet](../../debugger/debug-interface-access/symtagenum.md)   
 [Idiaenumsymbols –](../../debugger/debug-interface-access/idiaenumsymbols.md)   
 [Idiasession::findchildren –](../../debugger/debug-interface-access/idiasession-findchildren.md)   
 [NameSearchOptions – výčet](../../debugger/debug-interface-access/namesearchoptions.md)