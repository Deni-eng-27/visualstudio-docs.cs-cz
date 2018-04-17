---
title: Programy | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], programs
- programs, debugging
ms.assetid: e1f955d8-95da-493b-837e-e97741a26d7e
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: dd3d1c1e72524c393fdb3adc4477ea9ae374fbfa
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="programs"></a>Programy
Z hlediska architektuře ladicího programu **program**:  
  
-   Je kontejner pro sadu vláken a sadu moduly. Program nemá žádné jednoho analogie v operačním systému Windows.  
  
     Druh podproces je program. Například při ladění webu, můžete zobrazit skriptu jako programu. Zatímco skript se spustí v procesu skriptovací stroje, nezávisle na jiné skripty, má také vlastní sadu vláken. Modul ladění (DE) připojí programu a ne k procesu nebo vlákna.  
  
-   Můžete určit samostatně a proces běží v a lze k se odpojit od a popisují DE, který byl vytvořen, pokud existuje. Program lze spustit, zastavit, pokračovat a ukončen.  
  
-   Můžete vytvořit výčet všech podprocesů. Program můžete také zadat vlastní datový proud zpětný překlad a můžete vytvořit výčet všech kontextů kód z daného dokumentu pozice.  
  
-   Je reprezentována [IDebugProgram2](../../extensibility/debugger/reference/idebugprogram2.md) rozhraní, vytvořili předtím, než je připojen programu, nebo jako součást procesu připojování, v závislosti na implementaci. Pokud port zobrazí programy procesu, vytvoří se každý program v souladu s odpovídající [IDebugProgramNode2](../../extensibility/debugger/reference/idebugprogramnode2.md) rozhraní předat jako argument k [AddProgramNode](../../extensibility/debugger/reference/idebugportnotify2-addprogramnode.md). Při ladění moduly taky vytvořit `IDebugProgram2` rozhraní představují programy, tyto programy nejsou vytvářena v souladu s uzlem programu. `IDebugProgramNode2` Rozhraní vytvořené Zavedenými se používají pro skutečné ladění při nebyla vytvořena v port se používají pouze pro zjišťování, které programy běží v procesu.  
  
## <a name="see-also"></a>Viz také  
 [Procesy](../../extensibility/debugger/processes.md)   
 [Program uzly](../../extensibility/debugger/program-nodes.md)   
 [Moduly](../../extensibility/debugger/modules.md)   
 [Koncepty ladicí program](../../extensibility/debugger/debugger-concepts.md)   
 [Ladění modulu](../../extensibility/debugger/debug-engine.md)   
 [Pozice dokumentu](../../extensibility/debugger/document-position.md)   
 [Kontext kódu](../../extensibility/debugger/code-context.md)   
 [IDebugProgram2](../../extensibility/debugger/reference/idebugprogram2.md)   
 [IDebugProgramNode2](../../extensibility/debugger/reference/idebugprogramnode2.md)   
 [AddProgramNode](../../extensibility/debugger/reference/idebugportnotify2-addprogramnode.md)