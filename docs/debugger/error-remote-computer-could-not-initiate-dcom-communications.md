---
title: 'Chyba: vzdálený počítač nemohl inicializovat komunikaci modelu DCOM | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: error-reference
f1_keywords:
- vs.debug.error.unmarshal_callback_failed
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
ms.openlocfilehash: 8a1f5216953adc1b257e432b1e4f1eb4d041b836
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "85460701"
---
# <a name="error-remote-computer-could-not-initiate-dcom-communications"></a>Chyba: Vzdálený počítač nemohl inicializovat komunikace modelu DCOM.
Při pokusu o komunikaci se vzdáleným počítačem s místním počítačem došlo k chybě modelu DCOM. Místní počítač je počítač, který je

 se spuštěnou sadou Visual Studio. K této chybě může dojít z několika důvodů:

- Místní počítač má zapnutou bránu firewall.

- Ověřování systému Windows ze vzdáleného počítače na místní počítač nepracuje.

### <a name="to-correct-this-error"></a>Oprava této chyby

1. Pokud má místní počítač zapnutou bránu Windows Firewall, přečtěte si téma [vzdálené ladění](../debugger/remote-debugging.md) , kde najdete pokyny ke konfiguraci brány firewall pro místní ladění.

2. Otestujte ověřování systému Windows tím, že se pokusíte otevřít sdílenou složku na místním počítači ze vzdáleného serveru.

3. Chcete-li obnovit ověřování systému Windows, zkuste oba počítače restartovat. Prověřte protokoly událostí v místních a vzdálených počítačích pro chyby protokolu Kerberos a požádejte správce domény o známé problémy.

## <a name="see-also"></a>Viz také
 [Vzdálené ladění](../debugger/remote-debugging.md)