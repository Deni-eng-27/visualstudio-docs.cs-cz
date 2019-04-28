---
title: Imachinedebugmanagerevents – rozhraní | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IMachineDebugManagerEvents interface
ms.assetid: 468de2f4-49e0-4f6f-ba0c-0f5f6832c092
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fcfcc2aed0fedefdc149b83e911d33cd3b54cdef
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62977627"
---
# <a name="imachinedebugmanagerevents-interface"></a>IMachineDebugManagerEvents – rozhraní
Signály změny ve spuštěném seznam aplikací, které spravuje správce počítače ladění. Toto rozhraní je možné pomocí ladicího programu integrovaného vývojového prostředí pro zobrazení seznamu dynamických aplikací.  
  
 Kromě metod zděděných z `IUnknown`, `IMachineDebugManagerEvents` rozhraní poskytuje následující metody.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IMachineDebugManagerEvents::onAddApplication](../../winscript/reference/imachinedebugmanagerevents-onaddapplication.md)|Zpracovává událost, když aplikace se přidá do běhu seznamu aplikací.|  
|[IMachineDebugManagerEvents::onRemoveApplication](../../winscript/reference/imachinedebugmanagerevents-onremoveapplication.md)|Zpracuje událost odebrání aplikace spouštění seznam aplikací.|