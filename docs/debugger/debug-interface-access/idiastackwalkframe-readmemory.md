---
title: "Idiastackwalkframe::readmemory – | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaStackWalkFrame::readMemory method
ms.assetid: 7ab0b525-a5a7-4692-acad-e8c00fa9ab9a
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 03750c990d259bab3a4942021e0b3ee8b1e0fd65
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idiastackwalkframereadmemory"></a>IDiaStackWalkFrame::readMemory
Přečte paměti z bitové kopie.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT readMemory (   
   MemoryTypeEnum type,  
   ULONGLONG va,  
   DWORD     cbData,  
   DWORD*    pcbData,  
   BYTE      data[]  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `type`  
 [v] Jeden z [MemoryTypeEnum – výčet](../../debugger/debug-interface-access/memorytypeenum.md) hodnot výčtu, která určuje druh paměti pro přístup.  
  
 `va`  
 [v] Virtuální adresu umístění obrázku má začínat čtení.  
  
 `cbData`  
 [v] Velikost vyrovnávací paměť dat v bajtech.  
  
 `pcbData`  
 [out] Vrátí počet bajtů vrácených. Pokud `data` je `NULL`, pak `pcbData` obsahuje celkový počet bajtů dat, které jsou k dispozici.  
  
 `data`  
 [out] Vyrovnávací paměť, která je pro vyplnění data ze zadaného umístění.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [Idiastackwalkframe –](../../debugger/debug-interface-access/idiastackwalkframe.md)