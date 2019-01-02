---
title: Volání událostí ladicího programu | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], events
ms.assetid: b3440ac3-80af-40c6-bef4-cbf00fa67885
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: b4b97ddde0e7cdcd258a8549f588257d90a365a5
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53857329"
---
# <a name="call-debugger-events"></a>Volání událostí ladicího programu
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
  
## <a name="see-also"></a>Viz také:  
 [Vytvoření vlastního ladicího stroje](../../extensibility/debugger/creating-a-custom-debug-engine.md)