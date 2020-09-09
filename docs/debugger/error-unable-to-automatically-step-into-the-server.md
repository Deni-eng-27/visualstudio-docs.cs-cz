---
title: 'Chyba: nepovedlo se automaticky krokovat na server | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: error-reference
f1_keywords:
- vs.debug.error.causality_no_server_response
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- remote debugging, notification error
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 647f51314d5506e817fa6982aa693b62f62125cf
ms.sourcegitcommit: ed4372bb6f4ae64f1fd712b2b253bf91d9ff96bf
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/09/2020
ms.locfileid: "89599914"
---
# <a name="error-unable-to-automatically-step-into-the-server"></a>Chyba: Automatické krokování s vnořením do serveru se nezdařilo.
Chyba čtení:

 Nelze automaticky krokovat se serverem. Ladicí program nebyl upozorněn před provedením vzdálené procedury.

 K této chybě může dojít, když se pokoušíte Krokovat s vnořením do webové služby (viz [krokování do webové služby XML](/previous-versions/zc57803s(v=vs.100))). Tato situace může nastat, kdykoli není [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] správně nastavena.

 Možné příčiny:

- Soubor web.config pro vaši [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] aplikaci nenastaví ladění na "true" v (viz [režim ladění v aplikacích ASP.NET](../debugger/how-to-enable-debugging-for-aspnet-applications.md)).

- [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)]Po instalaci sady Visual Studio byla nainstalována verze aplikace. [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] měla by být nainstalována před Visual Studio. Chcete-li tento problém vyřešit, opravte instalaci sady Visual Studio pomocí **ovládacího panelu Windows > programy a funkce** .

## <a name="see-also"></a>Viz také
- [Chyby a řešení potíží se vzdáleným laděním](../debugger/remote-debugging-errors-and-troubleshooting.md)
- [Vzdálené ladění](../debugger/remote-debugging.md)