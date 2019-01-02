---
title: TargetCLR | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: f9732480-287f-40f1-a4ff-b112e143b940
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ed0891715f6c9a0f4f89249a6ca5ac6415bad038
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53967119"
---
# <a name="targetclr"></a>TargetCLR
**TargetCLR** Určuje verzi common language runtime (CLR) do profilu je do aplikace načtena více než jedna verze modulu CLR.  
  
 Ve výchozím nastavení [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] nástrojů pro profilaci sady cílit na první verzi modulu CLR, který je načten aplikací.  
  
## <a name="syntax"></a>Syntaxe  
  
```cmd  
VSPerfCmd.exe {/Launch:AppName | /Attach:PID} /TargetCLR[:ClrVersion] [Options]   
```  
  
#### <a name="parameters"></a>Parametry  
 `ClrVersion`  
 Číslo verze modulu CLR. Použijte formát verze **vN.N.NNNNN**.  
  
## <a name="required-options"></a>Požadované možnosti  
 **TargetCLR** možnost se dá použít jenom s **spuštění** nebo **připojit** možnosti.  
  
 **Spuštění:** `AppName`  
 Zadaná aplikace spustí a začne profilu.  
  
 **Připojení:** `PID`  
 Spuštění profilu určeného procesu.  
  
## <a name="example"></a>Příklad  
 V tomto příkladu se používá možnost TargetCLR abyste měli jistotu, že je modul CLR verze 4.0.11003 profilována.  
  
```cmd  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp  
VSPerfCmd.exe /Launch:TestApp.exe /TargetCLR:v4.0.11003  
```