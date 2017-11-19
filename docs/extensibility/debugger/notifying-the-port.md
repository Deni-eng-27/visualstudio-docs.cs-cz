---
title: "Upozornění Port | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: ports, notification
ms.assetid: f9fce48e-7d4e-4627-a0fb-77b75428146a
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 91bedf387fe86c2bf2fefb34e643e581a37c15bf
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="notifying-the-port"></a>Upozornění portu
Po spuštění programu, port musí být upozorněni, následujícím způsobem:  
  
1.  Když na port obdrží nový uzel program, odešle událost vytvoření programu zpět na relaci ladění. Událost s ním představuje rozhraní, které představuje program.  
  
2.  Relaci ladění dotazy pro identifikátor modul ladění (DE), který můžete připojit k programu.  
  
3.  Kontroluje, zda DE je na seznamu povolených DEs pro daný program relaci ladění. Relaci ladění získá tento seznam z nastavení active programu na řešení, původně předaný balíček ladění.  
  
     DE musí být v seznamu povolených, jinak je DE nebude připojen k programu.  
  
 Prostřednictvím kódu programu, když na port nejprve obdrží nový uzel program, vytvoří se [IDebugProgram2](../../extensibility/debugger/reference/idebugprogram2.md) rozhraní představují program.  
  
> [!NOTE]
>  Tento model nelze zaměňovat s `IDebugProgram2` rozhraní vytvořit později modul ladění (DE).  
  
 Port odešle [IDebugProgramCreateEvent2](../../extensibility/debugger/reference/idebugprogramcreateevent2.md) událost vytvoření programu zpět do správce ladicí relace (SDM) prostřednictvím COM `IConnectionPoint` rozhraní.  
  
> [!NOTE]
>  Tento model nelze zaměňovat s `IDebugProgramCreateEvent2` rozhraní, které se odesílají DE později.  
  
 Společně s událostí rozhraní samotné, odešle port [IDebugPort2](../../extensibility/debugger/reference/idebugport2.md), [IDebugProcess2](../../extensibility/debugger/reference/idebugprocess2.md), a [IDebugProgram2](../../extensibility/debugger/reference/idebugprogram2.md) rozhraní, které představují port, zpracování, a v uvedeném pořadí programu. Volání SDM [IDebugProgram2::GetEngineInfo](../../extensibility/debugger/reference/idebugprogram2-getengineinfo.md) získat identifikátor GUID DE, který můžete ladit program. Identifikátor GUID byl původně získaný [IDebugProgramNode2](../../extensibility/debugger/reference/idebugprogramnode2.md) rozhraní.  
  
 SDM kontroluje, zda je DE je na seznamu povolených DEs. SDM získá tento seznam z nastavení active programu na řešení, původně předaný balíček ladění. DE musí být v seznamu povolených, jinak nebude se připojit k programu.  
  
 Jakmile je identita DE známá, SDM je připraven k připojení k programu.  
  
## <a name="see-also"></a>Viz také  
 [Spuštění programu](../../extensibility/debugger/launching-a-program.md)   
 [Připojení po spuštění](../../extensibility/debugger/attaching-after-a-launch.md)   
 [Ladění úlohy](../../extensibility/debugger/debugging-tasks.md)