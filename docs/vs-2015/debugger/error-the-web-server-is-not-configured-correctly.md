---
title: 'Chyba: Webový server není správně nakonfigurován. | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
f1_keywords:
- vs.debug.remote.projnotconfigured
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- debugger, Web application errors
ms.assetid: 875ba87f-c372-4126-8fe3-e33931cf26c0
caps.latest.revision: 25
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: c8579f54eea636f0c3ad61a28ad1e3c6d001da65
ms.sourcegitcommit: c496a77add807ba4a29ee6a424b44a5de89025ea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/24/2019
ms.locfileid: "54834088"
---
# <a name="error-the-web-server-is-not-configured-correctly"></a>Chyba: Webový server není správně nakonfigurovaný.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Mezi možné příčiny této chyby patří:  
  
-   Došlo k pokusu o ladění aplikace .NET Web, který byl zkopírován do jiného počítače, ručně přejmenovat nebo přesunout.  
  
-   Nemají dostatek připojení služby IIS. Další informace o nasazení webu do služby IIS najdete v tématu [vytvořit webovou stránku](http://www.iis.net/learn/get-started/getting-started-with-iis/create-a-web-site).  
  
-   Pokud se pokoušíte ladit aplikaci ASP.NET, najdete [publikování do služby IIS](https://docs.asp.net/en/latest/publishing/iis.html) pokyny k nasazení ke vzdálenému počítači se službou IIS 8 nebo novější, nebo [vzdálené ladění ASP.NET ve vzdáleném počítači7.5službyIIS](../debugger/remote-debugging-aspnet-on-a-remote-iis-7-5-computer.md) pokyny k nasazení na vzdálený počítač se systémem službu IIS 7.5.  
  
## <a name="see-also"></a>Viz také  
 [Ladění webových aplikací: Chyby a řešení potíží](../debugger/debugging-web-applications-errors-and-troubleshooting.md)
