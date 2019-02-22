---
title: 'Chyba: Nelze automaticky krokování s vnořením do serveru | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: troubleshooting
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
ms.openlocfilehash: e9d84f4c7f7f58ae980a266b436207c843926ae1
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56711732"
---
# <a name="error-unable-to-automatically-step-into-the-server"></a>Chyba: Nelze automaticky krokování s vnořením do serveru
Chyba čtení:

 Nepovedlo se automatické krokování s vnořením do serveru. Ladicí program nebyl upozorněn, než se provedl vzdálené procedury

 Této chybě může dojít, když se pokoušíte Krokovat s vnořením webové služby (viz [krokování do webové služby XML](https://msdn.microsoft.com/library/8e67de38-bf5f-41cc-a457-1b88ce63d764)). To může nastat, když [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] není správně nastavený.

 Možné příčiny:

- Soubor web.config pro vaše [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] aplikace v není nastaven na hodnotu "true" debug (naleznete v tématu [režim ladění v aplikacích ASP.NET](../debugger/how-to-enable-debugging-for-aspnet-applications.md)).

- Verze [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] instaloval po instalaci sady Visual Studio. [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] musí se nainstalovat před Visual Studio. Chcete-li tento problém vyřešit, použijte Windows **ovládací panely > programy a funkce** opravit instalaci sady Visual Studio.

## <a name="see-also"></a>Viz také
- [Chyby při vzdáleném ladění a jejich řešení](../debugger/remote-debugging-errors-and-troubleshooting.md)
- [Vzdálené ladění](../debugger/remote-debugging.md)