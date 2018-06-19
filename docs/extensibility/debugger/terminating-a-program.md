---
title: Ukončení programu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- programs, termination events
- debugging [Debugging SDK], terminating a program
ms.assetid: eedda0a3-5e05-44fe-841d-a2f4866ac72d
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: bc5d711783b3238c9cfe42ba3fc4edd776bcb060
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31126735"
---
# <a name="terminating-a-program"></a>Ukončení programu
Následuje popis ukončení jeden program s jedno vlákno.  
  
## <a name="termination-process"></a>Ukončení procesu  
  
1.  Odešle DE [IDebugThreadDestroyEvent2](../../extensibility/debugger/reference/idebugthreaddestroyevent2.md) platný [IDebugThread2](../../extensibility/debugger/reference/idebugthread2.md).  
  
2.  Odešle DE [IDebugProgramDestroyEvent2](../../extensibility/debugger/reference/idebugprogramdestroyevent2.md) platný [IDebugProgram2](../../extensibility/debugger/reference/idebugprogram2.md).  
  
 Prostředí IDE přejde do režimu návrhu. Ladění modul nebo volání běhové prostředí [IDebugPortNotify2::RemoveProgramNode](../../extensibility/debugger/reference/idebugportnotify2-removeprogramnode.md) odebrání programu z portu.  
  
## <a name="see-also"></a>Viz také  
 [Volání událostí ladicího programu](../../extensibility/debugger/calling-debugger-events.md)