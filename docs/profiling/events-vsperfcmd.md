---
title: Události (VSPerfCmd) | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: eb139327-4783-4f2a-874c-efad377a7be4
author: mikejo5000
ms.author: mikejo
manager: jillfra
monikerRange: vs-2017
ms.workload:
- multiple
ms.openlocfilehash: 46b47f9b615c824d25e931cd3d05f5d2a04257ba
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "74777318"
---
# <a name="events-vsperfcmd"></a>Události (VSPerfCmd)
Možnost *VSPerfCmd.exe* **události**VSPerfCmd.exeřídí protokolování událostí pro Windows (ETW). Data ETW se ukládají do souboru. ETL, který je oddělený od datového souboru profileru. Data je možné zobrazit v sestavě pomocí příkazu [VSPerfReport](../profiling/vsperfreport.md) /Summary: ETW.

 Možnost **události** může být volána kdykoli před voláním příkazu VSPerfCmd **shutdown** pro zastavení profilování.

## <a name="syntax"></a>Syntaxe

```cmd
VSPerfCmd.exe /events {On|Off} {Guid|ProviderName} [,Flags[,Level]
```

#### <a name="parameters"></a>Parametry
 **Zapnutý** **&#124;spustí** nebo zastaví shromažďování dat událostí.

 `Guid` Identifikátor GUID ovládacího prvku poskytovatele

 `ProviderName` Název zprostředkovatele registrovaného pomocí rozhraní WMI (Windows Management Instrumentation) (WMI).

 `Flags` "0x"-předem opravené hexadecimální hodnoty, které jsou definovány poskytovatelem událostí.

 `Level` Určuje množství shromažďovaných dat. `Level` je definován poskytovatelem událostí.

 Možnost **události** rozumí následujícím klíčovým slovům jádra jako názvům zprostředkovatelů:

 **Zpracování** Zpracování událostí

 **Podproces** Události vlákna

 **Obrázek** Události načítání a uvolňování obrázku

 **Disk** Události v/v disku

 **Soubor** Vstupně výstupní události souboru

 **Hardfault** Závažné chyby stránky

 **Pagefault** Měkké chyby stránky

 **Síť** Události sítě

 **Registr** Události přístupu k registru

 Počítejte s tím, že zprostředkovatele jádra lze povolit pouze. Nedá se zakázat, ani změnit jejich příznaky, dokud se monitorování neukončí.

## <a name="remarks"></a>Poznámky

> [!NOTE]
> Pokud jsou povoleny události modulu CLR ETW, jsou v sestavě zobrazení trasování také shromažďována další spouštěcí data. Pokud chcete vyloučit události spuštění v sestavě, použijte následující příkaz:

```cmd
C:\<path>VSPerfCmd -events on, \".NET Common Language Runtime\", 0x7fffffff, 5
```

> [!IMPORTANT]
> Pokud nechcete události po spuštění vyloučit, protože tyto události nejsou uvedené v souboru formát MOF (Managed Object Format) (MOF), zobrazí se v sestavě jako identifikátory GUID. Další informace naleznete na této stránce na webu společnosti Microsoft: [vzorový soubor formát MOF (Managed Object Format) (MOF)](https://msdn.microsoft.com/library/default.aspx).

## <a name="see-also"></a>Viz také
- [VSPerfCmd](../profiling/vsperfcmd.md)
- [Profilovat samostatné aplikace](../profiling/command-line-profiling-of-stand-alone-applications.md)
- [ASP.NET webové aplikace Profile](../profiling/command-line-profiling-of-aspnet-web-applications.md)
- [Profilovací služby](../profiling/command-line-profiling-of-services.md)
