---
title: "Uživatel (VSPerfCmd) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ee1a478e-374d-4f30-ae28-d260b9d4723a
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5c6c442da6bad7ce2a718b58c98bae8cd559576a
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="user-vsperfcmd"></a>Uživatel (VSPerfCmd)
**Uživatele** možnost určuje, doména a uživatelské jméno účtu, který vlastní PROFILOVANÉHO proces. Tato možnost je vyžaduje jenom v případě, že je proces spuštěný jako uživatel, než je přihlášený uživatel. Vlastník proces je uvedena ve sloupci uživatelské jméno na kartě procesy ve Správci úloh systému Windows.  
  
 **Uživatele** možnost lze zadat pouze na příkazový řádek, který obsahuje také **spustit** možnost.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
VSPerfCmd.exe /Start:Method /Output:FileName /User:[Domain\]UserName [Options]  
```  
  
#### <a name="parameters"></a>Parametry  
 `Domain`  
 Název domény uživatele.  
  
 `UserName`  
 Jméno uživatele.  
  
## <a name="required-options"></a>Požadované možnosti  
 **Uživatele** možnost lze použít pouze s **spustit** možnost.  
  
 **Začátek:**`Method`  
 Inicializuje profileru pro zadanou metodu profilování.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití **uživatele** možnost.  
  
```  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp /User:SYSTEM  
```  
  
## <a name="see-also"></a>Viz také  
 [Vsperfcmd –](../profiling/vsperfcmd.md)   
 [Profilace samostatných aplikací](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Profilace webových aplikací ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profilace služeb](../profiling/command-line-profiling-of-services.md)