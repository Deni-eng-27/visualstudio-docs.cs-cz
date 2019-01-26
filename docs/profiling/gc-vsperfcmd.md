---
title: Uvolňování paměti (VSPerfCmd) | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 7c81e88b-a748-4cf5-a7a1-3429608e1b54
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a97b45c9bc9db61e579430bb3e2ceeb48206ef50
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54992448"
---
# <a name="gc-vsperfcmd"></a>Uvolňování paměti (VSPerfCmd)
**GC** možnost povoluje shromažďování dat rozhraní .NET Framework paměť přidělení a objekt životnost. **Uvolňování paměti** možnost jde použít jenom s metoda profilování vzorkování a jenom **spuštění** možnost.  
  
 Při použití **GC** možnost, VSPerfClrEnv **/sampleon** příkazu se nevyžaduje.  
  
 Pokud nejsou zadány žádné parametry, nebo pokud **přidělení** parametr zadán, jsou shromažďovány pouze rozhraní .NET Framework data o přidělování paměti. Pokud **životnost** parametr zadán, přidělení paměti rozhraní .NET Framework a .NET Framework objekt se shromažďují data o životním cyklu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cmd  
VSPerfCmd.exe /Launch:AppName /GC[:{Allocation|Lifetime}] [Options]  
```  
  
#### <a name="parameters"></a>Parametry  
 **přidělení**  
 Default (Výchozí). Shromažďuje data o přidělování paměti rozhraní .NET Framework.  
  
 **Doba platnosti**  
 Shromažďuje data o přidělování paměti rozhraní .NET Framework a .NET Framework data o životním cyklu objektu.  
  
## <a name="required-options"></a>Požadované možnosti  
 **GC** možnost se dá použít jenom s **spuštění** možnost.  
  
 **Spuštění:** `AppName`  
 Zadaná aplikace spustí a začne profilace pomocí metody odběru vzorků.  
  
## <a name="example"></a>Příklad  
 Následující příklad spustí aplikaci a shromažďuje data o přidělování paměti rozhraní .NET Framework.  
  
```cmd  
VSPerfCmd.exe /Launch:TestApp.exe /gc  
```  
  
## <a name="see-also"></a>Viz také:  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [Samostatné aplikace profilu](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Webové aplikace ASP.NET profilu](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profil služby](../profiling/command-line-profiling-of-services.md)