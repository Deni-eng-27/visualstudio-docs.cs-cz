---
title: Historické ladění | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 7cc5ddf2-2f7c-4f83-b7ca-58e92e9bfdd2
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: dc16c6e6186d53bd08bd0634e07a4d1172859280
ms.sourcegitcommit: 5a65ca6688a2ebb36564657d2d73c4b4f2d15c34
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/16/2019
ms.locfileid: "54227249"
---
# <a name="historical-debugging-c-visual-basic-c"></a>Historické ladění (C#, Visual Basic, C++)

Historické ladění je režim ladění, který závisí na informace shromážděné funkcí technologie IntelliTrace. Umožňuje přejít zpět a vpřed prostřednictvím spuštění vaší aplikace a zkontrolovat její stav.  
  
 Můžete použít nástroj IntelliTrace v sadě Visual Studio Enterprise edition (ale ne edice Professional nebo Community).  
  
## <a name="why-use-historical-debugging"></a>Proč používat historické ladění?

 Nastavení zarážek, abyste odhalili chyby může být místo toho hit-or-miss záležitost. Nastavit zarážku blízko místa v kódu kde máte podezření na chybu na a pak spusťte aplikaci v ladicím programu a Doufáme, že zarážku získá přístupů a že na místě, kde se přeruší provádění může odhalit příčiny chyby. V opačném případě bude nutné vyzkoušet, nastavením zarážky někde jinde v kódu a znovu spusťte ladicí program, spuštění testovací kroky pořád dokola, dokud nalezení příčiny problému.  
  
 ![nastavením zarážky](../debugger/media/breakpointprocesa.png "BreakpointProcesa")  
  
 Můžete přesouvat kolem ve vaší aplikaci a zkontrolujte jeho stav (zásobník volání a místní proměnné) bez nutnosti nastavovat zarážky, restart ladění pomocí IntelliTrace a historické ladění a testovací kroky. To vám ušetří spoustu času, zejména při chyby se nachází hlouběji ve scénáři testu, která trvá dlouhou dobu spuštění.  
  
## <a name="how-do-i-start-using-historical-debugging"></a>Jak můžu začít používat historické ladění?

 Nástroj IntelliTrace je ve výchozím. Všechno, co musíte udělat, je rozhodnout, které událostí a volání funkce jsou vás zajímají, a určuje, zda chcete zobrazit snímky stavu vaší celou aplikaci. Další informace o definování co chcete hledat, naleznete v tématu [funkce IntelliTrace](../debugger/intellitrace-features.md). Podpora funkce se liší podle jazyka a aplikace typu.

 - Chcete-li zobrazit snímky pomocí historického ladění, naleznete v tématu [kontrolovat předchozí nové aplikace pomocí nástroje IntelliTrace](../debugger/view-historical-application-state.md)
 - Zjistěte, jak kontrolovat proměnné a vyhledání kódu, naleznete v tématu [Kontrola aplikace s využitím historického ladění](../debugger/historical-debugging-inspect-app.md)
 - Další informace o ladění pomocí událostí IntelliTrace, naleznete v tématu [názorný postup: Pomocí IntelliTrace](../debugger/walkthrough-using-intellitrace.md).