---
title: Časovač | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
ms.assetid: 1971868e-89fa-4452-8ee7-76e4daf31b66
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4b5998f90aeee14d903fdaa972166d61b0d2478c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="timer"></a>Časovač
VSPerfCmd.exe **časovače** možnost nastaví profilování událost, která je vzorkovat hodinových cyklů procesoru a volitelně změní počet cyklů v intervalu vzorkování z výchozí hodnotu 10 000 000. 10 000 000 hodinových cyklů procesoru (jeden GHz) 1GH, je přibližně 100 ukázky za sekundu. Minimální počet cykly, které lze zadat je 50 000.  
  
 **Časovač** lze použít pouze při použití metoda profilování se vzorkováním a lze použít pouze v příkazovém řádku, který také obsahuje **spusťte** nebo **Attach** možnost.  
  
 Ve výchozím nastavení událostí vzorkování profileru nastavena na výkon procesoru hodiny a interval vzorkování je nastaven na hodnotu 10 000 000. **Časovače**, **PF**, **Sys**, a **čítač** možnosti umožňují nastavit událostí vzorkování a intervalu vzorkování. **GC** možnost shromažďuje data paměti .NET v každé kolekci události přidělení a uvolňování paměti. Na příkazovém řádku lze zadat pouze jeden z těchto možností.  
  
 Vzorkování událostí a intervalu vzorkování lze nastavit pouze v první příkazového řádku, který obsahuje **spusťte** nebo **Attach** možnost.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
VSPerfCmd.exe {/Launch:AppName|/Attach:PID} /Timer[:Cycles] [Options]  
```  
  
#### <a name="parameters"></a>Parametry  
 `Cycles`  
 Celočíselná hodnota, která určuje počet cyklů procesoru hodiny v intervalu vzorkování. Pokud `Cycles` není zadán, interval je nastaven na hodnotu 10 000 000. Zadejte hodnotu bez čárkami.  
  
## <a name="required-options"></a>Požadované možnosti  
 **Časovač** lze zadat pouze na příkazový řádek, který obsahuje jeden z následujících možností.  
  
 **Spusťte:** `AppName`  
 Spustí profileru a aplikace určeného `AppName`.  
  
 **Připojení:** `PID`  
 Připojí profileru k proces zadaný pomocí ID procesu (`PID`).  
  
## <a name="invalid-options"></a>Neplatné možnosti  
 Nelze zadat následující možnosti na stejném příkazovém řádku jako **časovače**.  
  
 **PF**[**:**`Events`]  
 Nastaví událostí vzorkování na chyb stránek a volitelně nastaví interval vzorkování na `Events`. Výchozí interval PF je 10.  
  
 **Sys**[**:**`Events`]  
 Nastaví událostí vzorkování operační systém volá a volitelně nastaví interval vzorkování na `Events`. Výchozí interval Sys je 10.  
  
 **Čítač**[**:**`Name,Reload,FriendlyName`]  
 Nastaví událostí vzorkování na výkon procesoru čítač určeného `Name` a nastaví interval vzorkování na `Reload`.  
  
 **Globální Katalog**[**:**{**přidělení**&#124;**životnost**}]  
 Shromažďuje data paměti .NET. Ve výchozím nastavení (**přidělení**), data jsou shromažďována v každé události přidělení paměti. Když **životnost** je zadán parametr, data jsou shromažďována také v každé události kolekce paměti.  
  
## <a name="example"></a>Příklad  
 Tento příklad ukazuje, jak nastavit interval vzorkování profileru na 1 000 000 cyklů procesoru.  
  
```  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp  
VSPerfCmd.exe /Launch:TestApp.exe /Timer:1000000  
```  
  
## <a name="see-also"></a>Viz také  
 [Vsperfcmd –](../profiling/vsperfcmd.md)   
 [Profilace samostatných aplikací](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Profilace webových aplikací ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profilace služeb](../profiling/command-line-profiling-of-services.md)