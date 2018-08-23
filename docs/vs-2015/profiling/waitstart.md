---
title: WaitStart | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6c737177-2dfb-4150-963e-a49ac9aaa591
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e1e452fb46af37778a94dee271adf47a1255e1b8
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42671578"
---
# <a name="waitstart"></a>WaitStart
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [WaitStart](https://docs.microsoft.com/visualstudio/profiling/waitstart).  
  
Možnost WaitStart způsobí, že dílčí příkaz VSPerfCmd.exe Start vrátit pouze v případě, že profiler byl inicializován nebo po uplynutí zadaném počtu sekund. Ve výchozím nastavení, Start příkaz vrátí hodnotu okamžitě. Vrátí dílčí příkaz Start bez inicializace okna profilování, vrátí se chyba. Pokud není zadaný počet sekund, po neomezenou dobu čeká příkazu Start.  
  
 WaitStart možnost je užitečná v dávkových souborech a zajistit, že profiler byl inicializován.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
VSPerfCmd.exe /Start:Method /Output:FileName[Options] /StartWait[:Seconds]  
```  
  
#### <a name="parameters"></a>Parametry  
 `Seconds`  
 Počet sekund čekání před návratem z dílčích příkazu Start.  
  
## <a name="required-options"></a>Požadované možnosti  
 Možnost WaitStart jde použít jenom s dílčího příkazu Start.  
  
 **Výstup:** `filename`  
 Určuje název výstupního souboru.  
  
## <a name="remarks"></a>Poznámky  
  
## <a name="example"></a>Příklad  
 V tomto příkladu soubor batch příkazu Start. Počkejte 5 sekund kvůli na inicializaci profileru.  
  
```  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp /WaitStart:5  
if not %errorlevel% 0 goto :error_tag  
VSPerfCmd.exe /Launch:TestApp.exe  
goto :end  
:error_tag  
@echo Could not start Profiler!  
@echo Error %errorlevel%  
:end  
```



