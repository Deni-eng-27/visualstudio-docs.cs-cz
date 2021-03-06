---
title: WinCounter | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: ff319ffc-f249-4c3f-9eb2-06e392e3ae80
author: mikejo5000
ms.author: mikejo
manager: jillfra
monikerRange: vs-2017
ms.workload:
- multiple
ms.openlocfilehash: 672d472d4e592782f7ae06920c518b154fba6cba
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "85329876"
---
# <a name="wincounter"></a>WinCounter
Možnost **WinCounter** určuje čítač výkonu systému Windows nebo aplikace, který se má shromáždit v nastavených intervalech během spuštění profilu. Čítače výkonu pro systém Windows a aplikace jsou uvedeny jako značky v souboru dat profilování. Můžete zadat více čítačů výkonu ke shromáždění v samostatných možnostech.

 Ve výchozím nastavení se čítače shromažďují každých 500 milisekund. K určení intervalu jiné kolekce použijte možnost automatického **označení** .

 Je použita pouze jedna možnost automatického **označení** . Pokud jsou zadány vícenásobné možnosti automatického **označování** , použije se poslední z nich.

 Možnost **WinCounter** lze použít pouze s možností **Start** .

## <a name="syntax"></a>Syntaxe

```cmd
VSPerfCmd.exe /Start:Method /Wincounter:Path [/WinCounter:Path] [AutoMark:Milliseconds] [Options]
```

#### <a name="parameters"></a>Parametry
 `Path` Čítač výkonu systému Windows ve formátu cesty čítače PDH.

## <a name="required-options"></a>Požadované možnosti
 Možnost **WinCounter** lze použít pouze s možností **Start** .

 **Začátek:** `Method` Možnost **Spustit** inicializuje Profiler na určenou metodu profilace.

## <a name="exclusive-options"></a>Exkluzivní možnosti
 Možnost automatického **označení** lze použít pouze s možností **WinCounter** .

 Automatického **označení:** `Milliseconds` Určuje počet milisekund mezi shromažďováním dat čítače výkonu systému Windows.

## <a name="example"></a>Příklad
 V následujícím příkladu jsou zadány dva čítače výkonu systému Windows, které mají být shromažďovány v intervalu 1000 milisekund.

```cmd
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp /WinCounter:"\Processor(0)\% Processor Time" /WinCounter:"\System\Context Switches/sec" /AutoMark:1000
```

## <a name="see-also"></a>Viz také
- [VSPerfCmd](../profiling/vsperfcmd.md)
- [Profilovat samostatné aplikace](../profiling/command-line-profiling-of-stand-alone-applications.md)
- [ASP.NET webové aplikace Profile](../profiling/command-line-profiling-of-aspnet-web-applications.md)
- [Profilovací služby](../profiling/command-line-profiling-of-services.md)
