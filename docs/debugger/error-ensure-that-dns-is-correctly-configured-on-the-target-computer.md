---
title: 'Chyba: Ujistěte se, že DNS správně nakonfigurovaný v cílovém počítači | Dokumentace Microsoftu'
ms.date: 11/04/2016
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
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c538a2b4ff4a50cd89bd9571a8746ccb58aaed04
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62850876"
---
# <a name="error-ensure-that-dns-is-correctly-configured-on-the-target-computer"></a>Chyba: Ujistěte se, že DNS správně nakonfigurovaný v cílovém počítači
Při pokusu o provádět vzdálené ladění, může zobrazit následující chybová zpráva:

```cmd
Error: The Visual Studio Remote Debugger on the target computer cannot connect back to this computer. Ensure that DNS is correctly configured on the target computer.
```

 K této chybě dochází, když se cílový počítač nemůže přeložit název hostitelského počítače ladicího programu sady Visual Studio. Zkontrolujte nastavení DNS v cílovém počítači.

- Informace o zobrazení nastavení DNS ve Windows 8.1, Vista, Windows 7, Windows Server 2012, Windows Server 2008 nebo Windows Server 2008 R2, to provést: na **Start** nabídce zvolte **Nápověda a podpora** a poté vyhledejte **Změna nastavení protokolu TCP/IP**.

- Další informace najdete v části [webu Microsoft Windows](http://go.microsoft.com/fwlink/?LinkId=252720) a vyhledejte **Změna nastavení protokolu TCP/IP**.

  Pokud DNS problém nevyřešíte, pokuste se spustit vzdálený ladicí program pod jiným účtem. Tato chyba nastane pouze při spouštění vzdáleného ladicího programu v rámci místní systém nebo účet síťové služby. Při spuštění vzdáleného ladicího programu pod jiným účtem, může použít ověřování NTLM, která nevyžaduje DNS. . Tento postup, naleznete v tématu [Chyba: Služba Visual Studio Remote Debugger na cílovém počítači se nemůže připojit zpět k tomuto počítači](../debugger/error-the-visual-studio-remote-debugger-service-on-the-target-computer-cannot-connect-back-to-this-computer.md).
