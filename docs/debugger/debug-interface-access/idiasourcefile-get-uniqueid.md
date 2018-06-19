---
title: Idiasourcefile::get_uniqueid – | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSourceFile::get_uniqueId method
ms.assetid: e0b8dbc0-6061-4f31-bead-2cd72be44e41
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3714ce733b0388e3ac462a9495360171971a6750
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
ms.locfileid: "31460557"
---
# <a name="idiasourcefilegetuniqueid"></a>IDiaSourceFile::get_uniqueId
Načte jednoduché celočíselnou hodnotu klíče, které jsou jedinečné pro tuto bitovou kopii.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT get_uniqueId (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pRetVal`  
 [out] Vrací jednoduchý celočíselnou hodnotu klíče, které jsou jedinečné pro tuto bitovou kopii.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Porovnání klíčů místo řetězce můžou urychlit zpracování číslo řádku.  
  
## <a name="see-also"></a>Viz také  
 [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)