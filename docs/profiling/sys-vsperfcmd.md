---
title: Sys (VSPerfCmd) | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 294a6f9e-b49f-4c83-b322-5ac5411b66fb
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 5f0a63cfca8e06d999c585793fabdce627d4896d
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56634289"
---
# <a name="sys-vsperfcmd"></a>Sys (VSPerfCmd)
*VSPerfCmd.exe* **Sys** parametr nastaví profilování události, ke které se definuje tak, aby událostí volání systému (volání funkcí v profilované aplikace v operačním systému) a volitelně se mění číslo volání systému v intervalu vzorkování z výchozí hodnoty 10.

 **Sys** jde použít jenom v příkazovém řádku, který také obsahuje **spuštění** nebo **připojit** možnost.

 Ve výchozím nastavení událost odběru vzorků profiler je nastavena na hodinových cyklů procesoru a interval vzorkování je nastavený na 10 000 000. **Časovače**, **PF**, **Sys**, a **čítač** možnosti umožňují nastavit událost odběru vzorků a interval odběru vzorků. **GC** možnost shromažďuje data paměti .NET v každé události přidělování a uvolňování paměti kolekce. Na příkazovém řádku lze zadat pouze jeden z těchto možností.

 Událost odběru vzorků a interval vzorkování je možné nastavit pouze v první příkazového řádku, který obsahuje **spuštění** nebo **připojit** možnost.

## <a name="syntax"></a>Syntaxe

```cmd
VSPerfCmd.exe {/Launch:AppName|Attach:PID} /Sys[:Events] [Options]
```

#### <a name="parameters"></a>Parametry
 `Events` Celočíselná hodnota, která určuje počet systému volání události v intervalu vzorkování. Pokud `Events` není zadán, je nastavit interval na 10.

## <a name="required-options"></a>Požadované možnosti
 **Sys** vyžaduje jednu z následujících možností.

 **Spuštění:** `AppName` Spuštění profileru a aplikace určené `AppName`.

 **Připojení:** `PID` Připojí profiler k procesu určené `PID`.

## <a name="invalid-options"></a>Neplatné možnosti
 Tyto možnosti nelze zadat na stejném příkazovém řádku jako **Sys**.

 **PF**[**:**`Events`] Nastaví událost odběru vzorků na chyby stránek a volitelně nastaví interval vzorkování na `Events`. Výchozí interval PF je 10.

 **Časovač**[**:**`Cycles`] Nastaví událost odběru vzorků na hodin procesoru cykly a volitelně nastaví interval vzorkování na `Cycles`. Výchozí interval časovače je 10 000 000.

 **Čítač:** `Name`[`,Reload`[`,FriendlyName`]] Nastaví událost odběru vzorků na výkon procesoru čítač určené `Name` a nastaví interval vzorkování na `Reload`.

 **Uvolňování paměti**[**:**{**přidělení**&#124;**životnost**}] data paměti .NET shromažďuje. Ve výchozím nastavení (**přidělení**), data se shromažďují v každé události přidělení paměti. Když **životnost** parametr zadán, data se shromažďují také na všechny události uvolňování paměti kolekce.

## <a name="example"></a>Příklad
 Tento příklad ukazuje, jak nastavit profiler událost odběru vzorků na volání systému a jak nastavit interval vzorkování na 20 volání na vzorek.

```cmd
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp
VSPerfCmd.exe /Launch:TestApp.exe /Sys:20
```

## <a name="see-also"></a>Viz také:
- [VSPerfCmd](../profiling/vsperfcmd.md)
- [Samostatné aplikace profilu](../profiling/command-line-profiling-of-stand-alone-applications.md)
- [Webové aplikace ASP.NET profilu](../profiling/command-line-profiling-of-aspnet-web-applications.md)
- [Profil služby](../profiling/command-line-profiling-of-services.md)