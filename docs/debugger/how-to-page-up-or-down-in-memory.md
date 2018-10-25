---
title: 'Postupy: stránku nahoru nebo dolů v paměti | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
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
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 25c057687596e5f410c4a19f9a1c8c2cdef02f28
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/23/2018
ms.locfileid: "49816650"
---
# <a name="how-to-page-up-or-down-in-memory"></a>Postupy: O stránku nahoru nebo dolů v paměti
Při prohlížení obsah paměti **paměti** okno nebo **zpětný překlad** můžete použít svislý posuvník přesunout nahoru nebo dolů v paměti prostoru.  
  
### <a name="to-page-up-or-down-in-memory"></a>Na stránce nahoru nebo dolů v paměti  
  
1. Na stránce dolů (Přejít na vyšší adresy paměti), klikněte na svislý posuvník posuvníku.  
  
2. Na stránce nahoru (Přejít na nižší adresa paměti), klikněte na svislý posuvník nad jezdce.  
  
   Můžete si všimnout, že svislý posuvník funguje v nestandardním způsobem. Adresní prostor moderní počítače je velmi velké a je snadné získat ztráty uchopíte jeho thumb posuvník a jeho přetažením do náhodných umístění. Z tohoto důvodu jezdce je "springloaded" a vždy zůstane v centru posuvník. V nativním kódu aplikace můžete stránku nahoru nebo dolů ale nejde o volně přejděte.  
  
   Ve spravovaných aplikacích zpětného překladu je omezená na jednu funkci a můžete posouvat normálně.  
  
   Můžete si všimnout, že vyšší adresy se zobrazí v dolní části okna. Chcete-li zobrazit adresu vyšší musí přesunout dolů, nikoli nahoru.  
  
#### <a name="to-move-up-or-down-one-instruction"></a>Chcete-li přesunout nahoru nebo dolů jedna instrukce  
  
-   Klikněte na šipku v horní nebo dolní svislý posuvník.  
  
## <a name="see-also"></a>Viz také  
 [Paměť Windows](../debugger/memory-windows.md)   
 [Postupy: použití okna zpětného překladu](../debugger/how-to-use-the-disassembly-window.md)   
 [Zobrazení dat v ladicím programu](../debugger/viewing-data-in-the-debugger.md)