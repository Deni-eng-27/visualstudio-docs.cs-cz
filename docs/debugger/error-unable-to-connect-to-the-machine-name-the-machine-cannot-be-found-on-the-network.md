---
title: 'Chyba: Nelze se připojit k počítači &lt;název&gt;. Počítač se v síti nepodařilo najít. | Dokumenty Microsoft'
ms.date: 11/04/2016
ms.topic: troubleshooting
f1_keywords:
- vs.debug.remote.dcom_disabled
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- DCOM, unable to connect error
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b8eebd082df031161604bd04afe61d1aca652f6a
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60043281"
---
# <a name="error-unable-to-connect-to-the-machine-ltnamegt-the-machine-cannot-be-found-on-the-network"></a>Chyba: Nelze se připojit k počítači &lt;název&gt;. Počítač se v síti nepodařilo najít.
K tomuto chování dochází, pokud platí jedna z následujících podmínek:

- Připojení ke vzdálenému počítači bylo přerušeno.

- Váš uživatelský účet na vzdáleném počítači zakázaná.

- Vypršela platnost vašeho hesla na vzdáleném počítači.

### <a name="to-resolve-this-behavior"></a>Chcete-li vyřešit tento problém

- Ujistěte se, že místní počítač, tak vzdálenému počítači jsou ve stejné síti. K tomuto účelu použijte Průzkumník systému Microsoft Windows (nebo Průzkumníka souborů), k akci pro přístup ke vzdálenému počítači.

     – a –

- Ujistěte se, že je povolena uživatelský účet, který používáte pro připojení ke vzdálenému počítači.

     – a –

- Ujistěte se, že heslo, které používáte pro připojení ke vzdálenému počítači je platný a že nevypršela platnost.

## <a name="see-also"></a>Viz také
- [Vzdálené ladění](../debugger/remote-debugging.md)
- [Nastavení a příprava ladicího programu](../debugger/debugger-settings-and-preparation.md)