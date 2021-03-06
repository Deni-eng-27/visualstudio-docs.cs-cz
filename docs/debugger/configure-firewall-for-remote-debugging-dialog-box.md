---
title: Dialogové okno Konfigurace brány firewall pro vzdálené ladění | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.debug.firewallconfiguration
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- Configure Firewall for Remote Debugging dialog box
- remote debugging, configuring firewalls
- firewalls, configuring for remote debugging
ms.assetid: 5dff3393-fdeb-4129-a2f6-31f653107a82
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8a2511fc2adfa63ff28f8459f48cbdf4b4623ff5
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "72745667"
---
# <a name="configure-firewall-for-remote-debugging-dialog-box"></a>Dialogové okno Konfigurace brány firewall pro vzdálené ladění
Toto dialogové okno se zobrazí, když brána Windows Firewall zablokuje ladicí program, aby přijímal informace prostřednictvím sítě. Chcete-li pokračovat ve vzdáleném ladění, je nutné otevřít díru v bráně firewall, aby ladicí program mohl získat informace.

> [!CAUTION]
> Otevření otvoru v bráně firewall může váš počítač vystavit bezpečnostním hrozbám, které je brána firewall navržená k blokování. Otevření díry pro vzdálené ladění odblokuje porty 4020 a 4021 v aplikaci Visual Studio 2015. V jiných verzích sady Visual Studio se používají další čísla portů. Další informace najdete v tématu [Přiřazení portů vzdáleného ladicího programu](../debugger/remote-debugger-port-assignments.md). Kromě toho umožňuje ladicímu programu otevřít další porty. Další informace najdete v tématu [Konfigurace brány Windows Firewall pro vzdálené ladění](../debugger/configure-the-windows-firewall-for-remote-debugging.md).

## <a name="uielement-list"></a>Seznam prvků uživatelského rozhraní
 **Zrušit vzdálené ladění** Zruší pokus o vzdálené ladění. Nastavení zabezpečení vašeho počítače zůstane beze změny.

 **Odblokovat vzdálené ladění z počítačů v místní síti (podsíti)** Umožňuje vzdálené ladění počítačů v místní podsíti. To může v počítačích v místní podsíti otevřít ohrožení zabezpečení, ale brána firewall nadále zablokuje informace přicházející mimo podsíť.

 **Odblokovat vzdálené ladění z libovolného počítače** Umožňuje vzdálené ladění počítačů kdekoli v síti. Toto nastavení je nejnižší zabezpečení.

## <a name="see-also"></a>Viz také

- [Zabezpečení ladicího programu](../debugger/debugger-security.md)
- [Vzdálené ladění](../debugger/remote-debugging.md)
- [Ladění odkazu uživatelského rozhraní](../debugger/debugging-user-interface-reference.md)