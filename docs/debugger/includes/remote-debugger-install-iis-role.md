---
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.openlocfilehash: 62bdcd8109263cc86e13484d146e46f8e95c7198
ms.sourcegitcommit: d1824ab926ebbc4a8057163e0edeaf35cec57433
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/24/2018
---
Tyto kroky ukazují pouze základní konfiguraci služby IIS. Podrobnější informace, nebo nainstalovat do počítače s Windows Desktop, najdete v části [publikování do služby IIS](/aspnet/core/publishing/iis?tabs=aspnetcore2x#iis-configuration) nebo [IIS 8.0 pomocí technologie ASP.NET 3.5 a technologii ASP.NET 4.5](/iis/get-started/whats-new-in-iis-8/iis-80-using-aspnet-35-and-aspnet-45).

Pro operační systémy Windows Server, použijte **přidat role a funkce** Průvodce prostřednictvím **spravovat** odkaz nebo **řídicí panel** na odkaz v **správce serveru**. Na **role serveru** kroku, zaškrtněte políčko pro **webového serveru (IIS)**.

![Role webového serveru IIS je vybrali v kroku rolí vyberte server.](../media/remotedbg-server-roles-ws2012.png)

Na **služby rolí** kroku, vyberte služby rolí služby IIS požadavky nebo přijměte výchozí nastavení role služeb zadaný. Pokud plánujete nasadit pomocí nástroje nasazení webu, ujistěte se, že **IIS skripty a nástroje správy** je vybrána.

Pokračujte potvrzení postup instalace role Webový server a služby. Po instalaci role webového serveru (IIS) není nutné restartovat server nebo služby IIS.