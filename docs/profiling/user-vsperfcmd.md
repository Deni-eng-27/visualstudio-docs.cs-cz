---
title: Uživatel (VSPerfCmd) | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: ee1a478e-374d-4f30-ae28-d260b9d4723a
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c769081a4b7a166a0c5673dee3467e9413a28eea
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53947488"
---
# <a name="user-vsperfcmd"></a>Uživatel (VSPerfCmd)
**Uživatele** Určuje doménu a uživatelské jméno účtu vlastnícího profilovaný proces. Tato možnost je vyžadována, pouze pokud je proces spuštěn pod jiným než přihlášeným uživatelem. Vlastník procesu je uvedena ve sloupci uživatelské jméno na **procesy** karty ve Správci úloh Windows.  
  
 **Uživatele** možnost lze zadat pouze na příkazovém řádku, který také obsahuje **Start** možnost.  
  
## <a name="syntax"></a>Syntaxe  
  
```cmd  
VSPerfCmd.exe /Start:Method /Output:FileName /User:[Domain\]UserName [Options]  
```  
  
#### <a name="parameters"></a>Parametry  
 `Domain`  
 Název domény uživatele.  
  
 `UserName`  
 Jméno uživatele.  
  
## <a name="required-options"></a>Požadované možnosti  
 **Uživatele** možnost se dá použít jenom s **Start** možnost.  
  
 **Spusťte:** `Method`  
 Inicializuje možnost profileru zadané metodě profilování.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití **uživatele** možnost.  
  
```cmd  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp /User:SYSTEM  
```  
  
## <a name="see-also"></a>Viz také:  
 [Nástroj VSPerfCmd](../profiling/vsperfcmd.md)   
 [Samostatné aplikace profilu](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Webové aplikace ASP.NET profilu](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profil služby](../profiling/command-line-profiling-of-services.md)