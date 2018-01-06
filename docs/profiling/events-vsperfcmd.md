---
title: "Události (VSPerfCmd) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eb139327-4783-4f2a-874c-efad377a7be4
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 3cfbeaa9c11bdb24b561e0dfdc10e8ab2a10053a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="events-vsperfcmd"></a>Události (VSPerfCmd)
VSPerfCmd.exe **události** možnost řídí protokolování trasování událostí pro Windows (ETW). Data trasování událostí pro Windows je uložena na soubor .etl, která je oddělená od datový soubor profileru. Data lze zobrazit v sestavě pomocí [vsperfreport –](../profiling/vsperfreport.md) /summary:etw příkaz.  
  
 **Události** možnost lze volat kdykoli před VSPerfCmd **vypnutí** příkaz nazývá zastavíte profilování.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
VSPerfCmd.exe /events {On|Off} {Guid|ProviderName} [,Flags[,Level]  
```  
  
#### <a name="parameters"></a>Parametry  
 **Na**&#124; **Vypnout**  
 Spuštění nebo zastavení shromažďování dat událostí.  
  
 `Guid`  
 Identifikátor GUID ovládacího prvku zprostředkovatele.  
  
 `ProviderName`  
 Název zprostředkovatele, který je registrován s Windows Management Instrumentation (WMI).  
  
 `Flags`  
 "0 x"-předponu hexadecimální příznaky hodnotu, která je definována zprostředkovatelem událostí.  
  
 `Level`  
 Určuje množství dat shromažďovaných. `Level`Definuje zprostředkovatele událostí.  
  
 **Události** možnost jste srozuměni s tím následující jádra klíčová slova jako názvy zprostředkovatele:  
  
 **Proces**  
 Zpracování událostí  
  
 **Přístup z více vláken**  
 Události vláken  
  
 **Obrázek**  
 Bitovou kopii zatížení a uvolnit události  
  
 **Disk**  
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
  
```  
C:\<path>VSPerfCmd -events on, \".NET Common Language Runtime\", 0x7fffffff, 5  
```  
  
> [!IMPORTANT]
>  Pokud nevyloučíte události spuštění, pak vzhledem k tomu, že tyto události nejsou uvedené v souboru formátu MOF (Managed Object), zobrazí se jako identifikátory GUID sestavy. Další informace najdete v části této stránky na webu společnosti Microsoft: [Ukázka formátu MOF (Managed Object) soubor](http://go.microsoft.com/fwlink/?linkid=37118).  
  
## <a name="see-also"></a>Viz také  
 [Vsperfcmd –](../profiling/vsperfcmd.md)   
 [Profilace samostatných aplikací](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Profilace webových aplikací ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profilace služeb](../profiling/command-line-profiling-of-services.md)