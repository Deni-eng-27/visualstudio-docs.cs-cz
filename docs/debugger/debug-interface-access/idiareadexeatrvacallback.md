---
title: "Idiareadexeatrvacallback – | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaReadExeAtRVACallback interface
ms.assetid: b2892513-3952-4f99-9b98-60cb9b1fdc91
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 09a570f27200dc677d292d645973fae8f9460f95
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idiareadexeatrvacallback"></a>IDiaReadExeAtRVACallback
Umožňuje aplikaci klienta k poskytování bajtů spustitelný soubor určený relativní virtuální adresu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDiaReadExeAtRVACallback : IUnknown  
```  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Následující tabulka uvádí metody `IDiaReadExeAtRVACallback`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[Idiareadexeatrvacallback::readexecutableatrva –](../../debugger/debug-interface-access/idiareadexeatrvacallback-readexecutableatrva.md)|Přečte zadaný počet bajtů, počínaje zadaný relativní virtuální adresa (RVA) ze spustitelného souboru.|  
  
## <a name="remarks"></a>Poznámky  
 Toto rozhraní implementuje klientskou aplikaci chcete-li poskytovat bajtů ke spustitelnému souboru pomocí relativní virtuální adresy do souboru ke spustitelnému souboru. Pokud chcete použít absolutní posun, implementovat [idiareadexeatoffsetcallback –](../../debugger/debug-interface-access/idiareadexeatoffsetcallback.md) rozhraní.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Tato metoda je implementované klientská aplikace a předán [idiadatasource::loaddataforexe –](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md) metoda jako alternativní metoda pro čtení souboru.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: Dia2.h  
  
 Knihovna: diaguids.lib  
  
 Knihovny DLL: msdia80.dll  
  
## <a name="see-also"></a>Viz také  
 [Rozhraní (přístup k rozhraní SDK ladění)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [Idiadatasource::loaddataforexe –](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)   
 [Idiareadexeatoffsetcallback –](../../debugger/debug-interface-access/idiareadexeatoffsetcallback.md)