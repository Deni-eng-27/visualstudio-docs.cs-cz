---
title: Programy | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], programs
- programs, debugging
ms.assetid: e1f955d8-95da-493b-837e-e97741a26d7e
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: cd38fa74d43842bcb1a08c682049b9998bc11ab3
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60110112"
---
# <a name="programs"></a>Programy
V architektuře ladicího programu *program*:

- Je kontejner pro sadu vláken a sady modulů. Program nemá žádné jeden přirovnání v operačním systému Windows.

     Program je druh podproces. Například při ladění webu, skript se dají považovat za programu. Při spuštění skriptu v procesu skriptovací stroj nezávisle na jiné skripty také má svou vlastní sadu vláken. Ladicí stroj (DE) připojí k programu a nikoli do procesu nebo vlákna.

- Můžete identifikovat samostatně a běží v procesu. Program lze připojit k, být odpojen od a popisují DE, který byl vytvořen, pokud existuje. Program můžete také spustit, zastavit, pokračovat a být ukončen.

- Můžete zobrazit výčet všech podprocesů. Program lze také zadat vlastní datový proud zpětný překlad a můžete zobrazit výčet všech kontextech kód z daného dokumentu pozice.

- Je reprezentován [IDebugProgram2](../../extensibility/debugger/reference/idebugprogram2.md) rozhraní vytvořené předtím, než je připojen program, nebo jako součást procesu připojení, v závislosti na implementaci. Při port vytvoří výčet programy, které proces, každý program je vytvořena v souladu s odpovídající [IDebugProgramNode2](../../extensibility/debugger/reference/idebugprogramnode2.md) rozhraní předán jako argument [AddProgramNode](../../extensibility/debugger/reference/idebugportnotify2-addprogramnode.md). Ladicí stroj také vytvořit `IDebugProgram2` rozhraní k reprezentaci programy, tyto programy nejsou vytvářena v souladu s uzlem programu. `IDebugProgramNode2` Rozhraní vytvořené Zavedenými se používají pro skutečné ladění, zatímco vytvořených port se používá pouze pro zjištění, jaké programy jsou spuštěny v procesu.

## <a name="see-also"></a>Viz také:
- [Procesy](../../extensibility/debugger/processes.md)
- [Uzly programů](../../extensibility/debugger/program-nodes.md)
- [Moduly](../../extensibility/debugger/modules.md)
- [Koncepty ladicího programu](../../extensibility/debugger/debugger-concepts.md)
- [Ladicí stroj](../../extensibility/debugger/debug-engine.md)
- [Pozice dokumentu](../../extensibility/debugger/document-position.md)
- [Kontext kódu](../../extensibility/debugger/code-context.md)
- [IDebugProgram2](../../extensibility/debugger/reference/idebugprogram2.md)
- [IDebugProgramNode2](../../extensibility/debugger/reference/idebugprogramnode2.md)
- [AddProgramNode](../../extensibility/debugger/reference/idebugportnotify2-addprogramnode.md)