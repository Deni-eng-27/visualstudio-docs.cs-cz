---
title: "Idiasession::put_loadaddress – | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaSession::put_loadAddress method
ms.assetid: b157b245-1ea0-4b80-8962-d8b278dbc742
caps.latest.revision: "11"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3b12ef6fa6da9338346aa997ba16cb023548f138
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idiasessionputloadaddress"></a>IDiaSession::put_loadAddress
Nastaví adresu zatížení pro spustitelný soubor, který odpovídá na symboly v tomto úložišti symbol.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT put_loadAddress (   
   ULONGLONG NewVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `NewVal`  
 [v] Načtěte adresu pro spustitelný soubor.  
  
## <a name="remarks"></a>Poznámky  
 Symbol vlastnosti virtuální adresy (VA) se vypočítávají pomocí hodnoty této metody. Virtuální adresy nejsou vypočítat, pokud je tato vlastnost nastavena na nenulovou hodnotou.  
  
> [!NOTE]
>  Tato metoda musí volat, když získáte [idiasession –](../../debugger/debug-interface-access/idiasession.md) objektu a před zahájením práce objektu, pokud budete muset použít všechny virtuální vlastnosti na symboly.  
  
## <a name="see-also"></a>Viz také  
 [Idiasession –](../../debugger/debug-interface-access/idiasession.md)