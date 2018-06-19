---
title: Idiaframedata::get_program – | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaFrameData::get_program method
ms.assetid: 9201409e-b4b1-4e2e-a9f8-d17678ac538b
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2c78c6f1c2c6e8368efd86dc3ffa03a021e46da3
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
ms.locfileid: "31459594"
---
# <a name="idiaframedatagetprogram"></a>IDiaFrameData::get_program
Načte řetězec program, který se používá k výpočtu registrace nastavit před voláním funkce aktuální.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT get_program (   
   BSTR* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pRetVal`  
 [out] Vrátí řetězec programu.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`. Vrátí `S_FALSE` -li tato vlastnost není podporována. Jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Řetězec programu je posloupnost makra, která je za účelem vytvoření prologu interpretovat. Například typický zásobníku může použít program řetězec `"$T0 $ebp = $eip $T0 4 + ^ = $ebp $T0 ^ = $esp $T0 8 + ="`. Formát je zpětné polština zápis, kde operátory podle operandy. `T0` představuje proměnnou dočasné v zásobníku. Tento příklad provede následující kroky:  
  
1.  Přesuňte obsah registru `ebp` k `T0`.  
  
2.  Přidat `4` na hodnotu v `T0` adresu vytvořit, získat hodnotu z této adresy a uložení hodnoty v registru `eip`.  
  
3.  Získat hodnotu z adresy uložené v `T0` a uložit do registru tuto hodnotu `ebp`.  
  
4.  Přidat `8` na hodnotu v `T0` a uložit do registru tuto hodnotu `esp`.  
  
 Všimněte si, že řetězec programu je specifické pro procesor a konvence volání, nastavení pro funkci reprezentována aktuální rámec zásobníku.  
  
## <a name="see-also"></a>Viz také  
 [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)