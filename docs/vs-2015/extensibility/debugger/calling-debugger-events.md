---
title: Volání událostí ladicího programu | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], events
ms.assetid: b3440ac3-80af-40c6-bef4-cbf00fa67885
caps.latest.revision: 8
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 6c6a5e75ab97f44efd52ef648791658ded34d085
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54785233"
---
# <a name="calling-debugger-events"></a>Volání událostí ladicího programu
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Dojde k událostem v ladicími relacemi v určitém pořadí.  
  
## <a name="discussion"></a>Diskuse  
 Pro pochopení způsobu volání mezi ladicího stroje (DE) a správce ladění relace (SDM), představuje následující pořadí volání události, ke kterým dochází v typické ladicí relace:  
  
1.  [Připojení a odpojení programu](../../extensibility/debugger/attaching-and-detaching-to-a-program.md)  
  
2.  [Spuštění ladicího programu](../../extensibility/debugger/launching-the-debugger.md)  
  
3.  [Ukončení programu](../../extensibility/debugger/terminating-a-program.md)  
  
4.  [Vytvořením zarážky](../../extensibility/debugger/creating-a-breakpoint.md)  
  
5.  [Když vytvoří vazbu zarážky nebo stát nevázaných](../../extensibility/debugger/when-a-breakpoint-binds-or-becomes-unbound.md)  
  
6.  [Chyby zarážky](../../extensibility/debugger/breakpoint-errors.md)  
  
7.  [Dosažení zarážky](../../extensibility/debugger/hitting-a-breakpoint.md)  
  
8.  [Odstranění zarážky](../../extensibility/debugger/deleting-a-breakpoint.md)  
  
9. [Přechod do režimu přerušení](../../extensibility/debugger/entering-break-mode.md)  
  
10. [Krokování v režimu pozastavení](../../extensibility/debugger/stepping-in-break-mode.md)  
  
11. [Vyhodnocení výrazu v režimu pozastavení](../../extensibility/debugger/expression-evaluation-in-break-mode.md)  
  
12. [Zpracování výjimek](../../extensibility/debugger/exception-handling-visual-studio-sdk.md)  
  
## <a name="see-also"></a>Viz také  
 [Vytvoření vlastního ladicího stroje](../../extensibility/debugger/creating-a-custom-debug-engine.md)
