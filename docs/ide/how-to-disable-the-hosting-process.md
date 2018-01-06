---
title: "Postupy: zákaz procesu hostování | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- hosting process, disabling
- vshost.exe, disabling the hosting process
ms.assetid: 9157488d-737f-454b-8d8d-36f99de38bb0
caps.latest.revision: "10"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 9609f902c11291cd6892cf663ec8a343952ebaab
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-disable-the-hosting-process"></a>Postupy: Zákaz procesu hostování
Je-li povolen hostitelský proces, mohou být volání určitých rozhraní API ovlivněna. V těchto případech je pro vrácení správných výsledků nutné hostitelský proces zakázat.  
  
### <a name="to-disable-the-hosting-process"></a>Zakázání hostitelského procesu  
  
1.  Otevřete projekt spustitelné aplikace v aplikaci [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Projekty, které nevytváří spustitelné soubory (například knihovny tříd nebo projekty služeb) tuto možnost nemají.  
  
2.  Na **projektu** nabídky, klikněte na tlačítko **vlastnosti**.  
  
3.  Klikněte **ladění** kartě.  
  
4.  Vymazat **povolit sady Visual Studio proces hostování** zaškrtávací políčko.  
  
 Je-li hostitelský proces zakázán, nebudou k dispozici některé funkce pro ladění nebo může dojít k poklesu výkonu. Další informace najdete v tématu [ladění a proces hostování](../debugger/debugging-and-the-hosting-process.md).  
  
 Obecně, pokud je hostitelský proces zakázán, platí:  
  
-   Čas potřebný ke spuštění ladění aplikací [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] se zvýší.  
  
-   Vyhodnocení výrazu v době návrhu není k dispozici.  
  
-   Ladění v částečném vztahu důvěryhodnosti není k dispozici.  
  
## <a name="see-also"></a>Viz také  
 [Ladění a proces hostování](../debugger/debugging-and-the-hosting-process.md)   
 [Proces hostování (vshost.exe)](../ide/hosting-process-vshost-exe.md)   
 [Sestavení během vývoje aplikace](http://msdn.microsoft.com/en-us/c9497d62-3b7b-4449-88e8-cf27acc9efe6)