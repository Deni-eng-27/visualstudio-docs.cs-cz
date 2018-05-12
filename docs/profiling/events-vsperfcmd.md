---
title: Události (VSPerfCmd) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: eb139327-4783-4f2a-874c-efad377a7be4
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 352feacc59a129d24575408776e9ec075b1294ac
ms.sourcegitcommit: 046a9adc5fa6d6d05157204f5fd1a291d89760b7
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/11/2018
---
# <a name="events-vsperfcmd"></a>Události (VSPerfCmd)
VSPerfCmd.exe **události** možnost řídí protokolování trasování událostí pro Windows (ETW). Data trasování událostí pro Windows je uložena na soubor .etl, která je oddělená od datový soubor profileru. Data lze zobrazit v sestavě pomocí [vsperfreport –](../profiling/vsperfreport.md) /summary:etw příkaz.  
  
 **Události** možnost lze volat kdykoli před VSPerfCmd **vypnutí** příkaz nazývá zastavíte profilování.  
  
## <a name="syntax"></a>Syntaxe  
  
```cmd  
VSPerfCmd.exe /events {On|Off} {Guid|ProviderName} [,Flags[,Level]  
```  
  
#### <a name="parameters"></a>Parametry  
 **Na**&#124;**vypnuto**  
 Spuštění nebo zastavení shromažďování dat událostí.  
  
 `Guid`  
 Identifikátor GUID ovládacího prvku zprostředkovatele.  
  
 `ProviderName`  
 Název zprostředkovatele, který je registrován s Windows Management Instrumentation (WMI).  
  
 `Flags`  
 "0 x"-předponu hexadecimální příznaky hodnotu, která je definována zprostředkovatelem událostí.  
  
 `Level`  
 Určuje množství dat shromažďovaných. `Level` Definuje zprostředkovatele událostí.  
  
 **Události** možnost jste srozuměni s tím následující jádra klíčová slova jako názvy zprostředkovatele:  
  
 **Proces**  
 Zpracování událostí  
  
 **Přístup z více vláken**  
 Události vláken  
  
 **Obrázek**  
 Bitovou kopii zatížení a uvolnit události  
  
 **disk**  
 Vstupně-výstupní diskové události  
  
 **Soubor**  
 Vstupně-výstupní události  
  
 **Hardfault**  
 Hardwarových chyb stránky  
  
 **Pagefault**  
 Logicky stránkování  
  
 **Sítě**  
 Události sítě  
  
 **Registru**  
 Události přístupu k registru  
  
 Všimněte si, že zprostředkovatel jádra lze povolit pouze. Nelze zakázat, ani jeho příznaky se dá změnit, dokud se vypne sledování.  
  
## <a name="remarks"></a>Poznámky  
  
> [!NOTE]
>  Pokud jsou povolené CLR ETW – události, další spuštění data jsou shromažďována také v trasování zobrazit sestavu. Z uvedených v sestavě vyloučit události spuštění, použijte následující příkaz:  
  
```cmd  
C:\<path>VSPerfCmd -events on, \".NET Common Language Runtime\", 0x7fffffff, 5  
```  
  
> [!IMPORTANT]
>  Pokud nevyloučíte události spuštění, pak vzhledem k tomu, že tyto události nejsou uvedené v souboru formátu MOF (Managed Object), zobrazí se jako identifikátory GUID sestavy. Další informace najdete v části této stránky na webu společnosti Microsoft: [Ukázka formátu MOF (Managed Object) soubor](http://go.microsoft.com/fwlink/?linkid=37118).  
  
## <a name="see-also"></a>Viz také  
 [Vsperfcmd –](../profiling/vsperfcmd.md)   
 [Profilace samostatných aplikací](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Profilace webových aplikací ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profilace služeb](../profiling/command-line-profiling-of-services.md)