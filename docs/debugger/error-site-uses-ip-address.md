---
title: Lokalita používá IP adresu | Microsoft Docs
ms.date: 11/04/2016
ms.topic: error-reference
f1_keywords:
- vs.debug.error.webdbg_siteusesipaddress
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugger, Web application errors
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b869a536ca3445069d9caf84eb862e407dfbe6dc
ms.sourcegitcommit: 062615c058d2ff44751e8d0c704ccfa3c5543469
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/22/2020
ms.locfileid: "90852534"
---
# <a name="error-site-uses-ip-address"></a>Chyba: Server používá adresu IP
K této chybě dojde, když se ladicí program pokusí o automatické připojení k webové aplikaci, která používá IP adresu. K tomu dojde, pokud změníte **identifikaci** webu tak, aby **používala konkrétní IP adresu** ve službě IIS.

 Aby se automatické připojení fungovalo, je potřeba vytvořit projekt s konkrétní IP adresou a nikoli jenom názvem počítače. V opačném případě ladicí program změní název počítače na localhost, což způsobí selhání odeslání příkazu ladění službě IIS.

### <a name="to-correct-this-error"></a>Oprava této chyby

1. Místo toho použijte manuální připojení (z nabídky ladění vyberte **připojit k procesu**).

     —nebo—

2. Změnit nastavení **Identifikace webu služby IIS** .

## <a name="see-also"></a>Viz také
- [Ladění webových aplikací: chyby a řešení potíží](../debugger/debugging-web-applications-errors-and-troubleshooting.md)