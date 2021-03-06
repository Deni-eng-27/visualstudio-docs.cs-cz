---
title: Sledování vzdáleného ladění sady Microsoft Visual Studio na vzdáleném počítači nemá oprávnění pro připojení k tomuto počítači.
titleSuffix: ''
ms.custom: seodec18
ms.date: 11/04/2016
ms.topic: error-reference
f1_keywords:
- vs.debug.error.access_denied_oncallback
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- remote debugging, Windows version error
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e7baed5cc2c4c8dbaa01cd3dfadc386b6db1834c
ms.sourcegitcommit: 062615c058d2ff44751e8d0c704ccfa3c5543469
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/22/2020
ms.locfileid: "90851083"
---
# <a name="error-the-microsoft-visual-studio-remote-debugging-monitor-on-the-remote-computer-does-not-have-permission-to-connect-to-this-computer"></a>Chyba: Microsoft Visual Studio Remote Debugging Monitor na vzdáleném počítači nemá oprávnění pro připojení k tomuto počítači.

K této chybě dochází, pokud uživatel, který se pokouší spustit Sledování vzdáleného ladění sady Visual Studio (Msvsmon), nemá účet v místním počítači. K této chybě může dojít při vzdáleném ladění pomocí staršího ladicího stroje.

## <a name="to-fix-this-problem"></a>Chcete-li tento problém vyřešit

- Přidejte uživatelský účet do hostitelského počítače ladicího programu sady Visual Studio se stejným názvem a heslem jako uživatelský účet běžící na vzdáleném počítači s msvsmon.

   \- ani

- Spusťte msvsmon jako uživatel, který má oprávnění k volání do místního počítače. To znamená, že uživatel musí být uživatel domény a správce na počítači s msvsmon. Uživatelský účet, který se má spustit msvsmon, můžete určit jedním ze dvou způsobů:

  - Klikněte pravým tlačítkem na ikonu msvsmon a v místní nabídce vyberte **Spustit jako** .

    \- ani

  - Na příkazovém řádku spusťte příkaz `runas.exe` .

## <a name="see-also"></a>Viz také

- [Chyby a řešení potíží se vzdáleným laděním](../debugger/remote-debugging-errors-and-troubleshooting.md)
- [Vzdálené ladění](../debugger/remote-debugging.md)