---
title: Idebugthreadcall – rozhraní | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDebugThreadCall interface
ms.assetid: 9a9a9892-f310-4ef3-8db2-4f868be52d7e
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 89f0fba2f5210cdcf4bb8f17443f948cb9ba1f4e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63004857"
---
# <a name="idebugthreadcall-interface"></a>IDebugThreadCall – rozhraní
`IDebugThreadCall` Rozhraní obvykle implementují komponenty, která provede volání mezi vlákny pomocí `IDebugThread` zařazování implementace poskytuje správce ladění procesu (PDM).  
  
 Volání PDM `IDebugThreadCall` rozhraní v požadované vlákna a `IDebugThreadCall` odešle volání požadované implementace rozhraní. `IDebugThreadCall` Rozhraní přetypování informace o parametrech předané parametry odpovídající nahoru.  
  
 `IDebugThreadCall` Rozhraní je objekt typu free.  
  
## <a name="methods"></a>Metody  
 Kromě metod zděděných z `IUnknown`, `IDebugThreadCall` rozhraní poskytuje následující metody.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IDebugThreadCall::ThreadCallHandler](../../winscript/reference/idebugthreadcall-threadcallhandler.md)|Zpracovává volání ke spouštění kódu v jiném vlákně.|