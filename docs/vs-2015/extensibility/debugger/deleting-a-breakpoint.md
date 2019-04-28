---
title: Odstranění zarážky | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- breakpoints, deleting
- debugging [Debugging SDK], deleting breakpoints
ms.assetid: 75a046cc-d20a-4c79-ad2d-1f18426ac5d0
caps.latest.revision: 8
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 42cd353c216c21d14c4f6592da809c72acdba664
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63409408"
---
# <a name="deleting-a-breakpoint"></a>Odstranění zarážky
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Následující část popisuje proces při odstraňování čekající zarážkou:  
  
## <a name="deletion-process"></a>Proces odstraňování  
 Správce ladění relace (SDM) volá [IDebugPendingBreakpoint2::Delete](../../extensibility/debugger/reference/idebugpendingbreakpoint2-delete.md) metoda odebrání čekající zarážka a všechny vazby zarážky vázán z něj.  
  
> [!NOTE]
> Jeden vázaná zarážka může také odstranit volání [IDebugBoundBreakpoint2::Delete](../../extensibility/debugger/reference/idebugboundbreakpoint2-delete.md).  
  
## <a name="see-also"></a>Viz také  
 [Volání událostí ladicího programu](../../extensibility/debugger/calling-debugger-events.md)
