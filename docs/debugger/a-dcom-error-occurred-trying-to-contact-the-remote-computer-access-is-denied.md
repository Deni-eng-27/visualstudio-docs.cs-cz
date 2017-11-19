---
title: "Při pokusu o obraťte se na vzdáleném počítači došlo k chybě DCOM. Přístup byl odepřen. | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug.remote.dcom_access_denied
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- remote debugging, DCOM error
- remote DCOM access denied error
- DCOM, access errors
ms.assetid: 9d7dfc1b-9fe0-4f54-9c50-9c0e0f8358c5
caps.latest.revision: "27"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fe153a5252603cf967b396932a6479a8df437a08
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="a-dcom-error-occurred-trying-to-contact-the-remote-computer-access-is-denied"></a>Při pokusu o obraťte se na vzdáleném počítači došlo k chybě DCOM. Přístup byl odepřen.
Vzdálené ladění používá model DCOM ke komunikaci mezi místních i vzdálených počítačů v následujících situacích:  
  
-   Ladicí program je nastaven na **nativní režim kompatibility** nebo **spravovaný režim kompatibility** se změnami **nástroje > Možnosti > ladění** stránky  
  
-   Ladění spravovaného C++ (C + +/ CLI) kódu.  
  
-   V sadě Visual Studio 2013 když **Povolit nativní upravit a pokračovat** se změnami **nástroje > Možnosti > ladění** stránky  
  
-   Některé třetích stran ladění scénáře  
  
 K této chybě dojde, když proces sady Visual Studio nemůže ověřit samotné (nebo zadané přihlašovací údaje byly za nedostatečné) pro proces vzdáleného ladicího programu přes model DCOM. Problém může vyřešit jeden nebo více z následujících řešení:  
  
-   Vypnout **nativní režim kompatibility** a **spravovaný režim kompatibility**.  
  
-   V sadě Visual Studio 2013, vypněte **Povolit nativní upravit a pokračovat**.  
  
-   Oba počítače restartujte.  
  
-   Pokud vzdálené ladění vyžaduje zadání přihlašovacích údajů, zaškrtněte možnost pro uložení přihlašovacích údajů.  
  
## <a name="see-also"></a>Viz také  
 [Vzdálené ladění chyby a řešení potíží](../debugger/remote-debugging-errors-and-troubleshooting.md)   
 [Vzdálené ladění](../debugger/remote-debugging.md)