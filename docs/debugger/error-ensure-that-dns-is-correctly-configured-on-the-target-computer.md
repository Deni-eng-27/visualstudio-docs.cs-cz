---
title: 'Chyba: Ověřte, zda je server DNS správně nakonfigurovaný v cílovém počítači | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: troubleshooting
f1_keywords:
- vs.debug.error.callback_dns_failed
dev_langs:
- CSharp
- VB
- FSharp
- C++
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0d2d945376f093e7df437751127c544b349458fd
ms.sourcegitcommit: 0bf2aff6abe485e3fe940f5344a62a885ad7f44e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/27/2018
ms.locfileid: "37056095"
---
# <a name="error-ensure-that-dns-is-correctly-configured-on-the-target-computer"></a>Chyba: Ověřte, zda je na cílovém počítači správně nakonfigurován server DNS.
Při pokusu provést vzdálené ladění, zobrazí se následující chybová zpráva:  
  
```cmd
Error: The Visual Studio Remote Debugger on the target computer cannot connect back to this computer. Ensure that DNS is correctly configured on the target computer.  
```  
  
 K této chybě dojde, když se cílový počítač nelze přeložit název hostitelského počítače ladicího programu sady Visual Studio. Zkontrolujte nastavení služby DNS v cílovém počítači.  
  
-   Informace o zobrazení vaše nastavení DNS ve Windows 8.1, Vista, Windows 7, Windows Server 2012, Windows Server 2008 nebo Windows Server 2008 R2, tomu: na **spustit** nabídce zvolte **Nápověda a podpora** a poté vyhledejte **Změna nastavení protokolu TCP/IP**.  
  
-   Další informace, přejděte na [webu Microsoft Windows](http://go.microsoft.com/fwlink/?LinkId=252720) a vyhledejte **Změna nastavení protokolu TCP/IP**.  
  
 Pokud DNS problém nevyřešíte, pokuste se spustit vzdáleného ladicího programu pod jiným účtem. K této chybě dojde pouze v případě, že je spuštěné vzdáleného ladicího programu pod místní systém nebo účet Network Service. Pokud spustíte vzdáleného ladicího programu pod jiným účtem, může použít ověřování NTLM, která nevyžaduje DNS. . Postup najdete v tématu [chybě: Visual Studio vzdáleného ladicího programu service v cílovém počítači se nemůže připojit zpět k tomuto počítači](../debugger/error-the-visual-studio-remote-debugger-service-on-the-target-computer-cannot-connect-back-to-this-computer.md).
