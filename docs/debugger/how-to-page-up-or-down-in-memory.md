---
title: 'Postupy: Stránku nahoru nebo dolů v paměti | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- debugger, paging up or down in memory
- memory, paging up or down
- Disassembly window, viewing memory space
- Memory window, paging up or down in memory
ms.assetid: 50b30a68-66f6-43f8-a48b-59ce12c95471
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4b8452100eb744d019c0f4c8d5e62566ac761210
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60072745"
---
# <a name="how-to-page-up-or-down-in-memory"></a>Postupy: Stránku nahoru nebo dolů v paměti

Při prohlížení obsah paměti **paměti** okno nebo **zpětný překlad** můžete použít svislý posuvník přesunout nahoru nebo dolů v paměti prostoru.

### <a name="to-page-up-or-down-in-memory"></a>Na stránce nahoru nebo dolů v paměti

1. Na stránce dolů (Přejít na vyšší adresy paměti), klikněte na svislý posuvník posuvníku.

2. Na stránce nahoru (Přejít na nižší adresa paměti), klikněte na svislý posuvník nad jezdce.

   Můžete si všimnout, že svislý posuvník funguje v nestandardním způsobem. Adresní prostor moderní počítače je velmi velké a je snadné získat ztráty uchopíte jeho thumb posuvník a jeho přetažením do náhodných umístění. Z tohoto důvodu jezdce je "springloaded" a vždy zůstane v centru posuvník. V nativním kódu aplikace můžete stránku nahoru nebo dolů ale nejde o volně přejděte.

   Ve spravovaných aplikacích zpětného překladu je omezená na jednu funkci a můžete posouvat normálně.

   Můžete si všimnout, že vyšší adresy se zobrazí v dolní části okna. Chcete-li zobrazit adresu vyšší musí přesunout dolů, nikoli nahoru.

#### <a name="to-move-up-or-down-one-instruction"></a>Chcete-li přesunout nahoru nebo dolů jedna instrukce

- Klikněte na šipku v horní nebo dolní svislý posuvník.

## <a name="see-also"></a>Viz také
- [Okna paměti](../debugger/memory-windows.md)
- [Postupy: Použití okna zpětného překladu](../debugger/how-to-use-the-disassembly-window.md)
- [Zobrazení dat v ladicím programu](../debugger/viewing-data-in-the-debugger.md)