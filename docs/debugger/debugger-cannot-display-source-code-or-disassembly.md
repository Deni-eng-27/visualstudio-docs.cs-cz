---
title: Ladicí program nemůže zobrazit zdrojový kód nebo zpětný překlad
ms.custom: seodec18
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- disassembly code, errors
ms.assetid: 112d3ea3-fdd2-4bce-92b4-167a76258934
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 466f8103b2b61d9922621ff2734dc88a20cd36bf
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56683971"
---
# <a name="debugger-cannot-display-source-code-or-disassembly"></a>Ladicí program nemůže zobrazit zdrojový kód nebo zpětný překlad.
Přečte tuto chybu:

 Ladicí program nemůže zobrazit zdrojový kód nebo zpětný překlad pro aktuální umístění, kde vykonávání se zastavilo.

 K této chybě může dojít z několika důvodů:

-   Můžete narazit zarážku v umístění, pro který neexistuje žádný zdrojový kód při ladění v jazyce, který nepodporuje zpětný překlad. Otevřít **zarážky** okna, vyhledejte zarážku zase ho smažete.

-   Když provádíte ladění skriptu, můžete narazit zarážky během nebyly žádná vlákna ve svém programu. Zvolte **krok** nebo **pokračovat** z **ladění** nabídky pokračovat v ladění.

-   Důležité informace o zabezpečení může znemožnit ladicího programu ze zásobníku a vlákna, zápis a další informace o kontextu čtením program, který ladíte. Toto je nejčastěji dochází, pokud jsou ladění webové aplikace a nemáte správná oprávnění pro přístup k virtuálnímu adresáři. Nastavení zabezpečení pro virtuální adresář pro anonymní a zkuste to znovu.

## <a name="see-also"></a>Viz také
- [Ladění v sadě Visual Studio](../debugger/index.md)
- [První seznámení s ladicím programem](../debugger/debugger-feature-tour.md)
- [Zobrazení dat v ladicím programu](../debugger/viewing-data-in-the-debugger.md)