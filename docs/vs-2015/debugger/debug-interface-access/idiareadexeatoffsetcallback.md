---
title: IDiaReadExeAtOffsetCallback | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaReadExeAtOffsetCallback interface
ms.assetid: 3c961641-3ce3-4bc3-bd6e-a802fa3bec49
caps.latest.revision: 10
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: f7e24257402ddb546df63753bed62add2d33c512
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "62538353"
---
# <a name="idiareadexeatoffsetcallback"></a>IDiaReadExeAtOffsetCallback
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Umožňuje klientské aplikaci poskytovat bajty spustitelného souboru, jak je uvedeno v umístění souboru.  
  
## <a name="syntax"></a>Syntax  
  
```  
IDiaReadExeAtOffsetCallback : IUnknown  
```  
  
## <a name="methods-in-vtable-order"></a>Metody v pořadí vtable  
 V následující tabulce jsou uvedeny metody `IDiaReadExeAtOffsetCallback` .  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IDiaReadExeAtOffsetCallback::ReadExecutableAt](../../debugger/debug-interface-access/idiareadexeatoffsetcallback-readexecutableat.md)|Přečte zadaný počet bajtů od zadaného posunu ze spustitelného souboru.|  
  
## <a name="remarks"></a>Poznámky  
 Klientská aplikace implementuje toto rozhraní, aby poskytovala bajty spustitelných souborů pomocí absolutního posunu do souboru spustitelného souboru. Chcete-li použít relativní virtuální adresu, implementujte rozhraní [IDiaReadExeAtRVACallback](../../debugger/debug-interface-access/idiareadexeatrvacallback.md) .  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Tato metoda je implementována klientskou aplikací a předána metodě [IDiaDataSource:: loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md) jako alternativní metodu pro čtení souboru.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: Dia2. h  
  
 Knihovna: diaguids. lib  
  
 KNIHOVNA DLL: msdia80.dll  
  
## <a name="see-also"></a>Viz také  
 [Rozhraní (Debug Interface Access SDK)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [IDiaDataSource:: loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)   
 [IDiaReadExeAtRVACallback](../../debugger/debug-interface-access/idiareadexeatrvacallback.md)
