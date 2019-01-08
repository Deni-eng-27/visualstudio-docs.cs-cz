---
title: Výčet SCRIPT_ERROR_DEBUG_EXCEPTION_THROWN_KIND | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: b3aa4966-e110-4b30-b368-1281a9740dbd
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 997c5149467591a7612e6ff10b0efcc3efbc91bf
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54087799"
---
# <a name="scripterrordebugexceptionthrownkind-enumeration"></a>Výčet SCRIPT_ERROR_DEBUG_EXCEPTION_THROWN_KIND
Označuje druh vyvolané výjimky. Tento výčet je používán [IActiveScriptErrorDebug110::GetExceptionThrownKind](../../winscript/reference/iactivescripterrordebug110-getexceptionthrownkind.md) metody.  
  
> [!IMPORTANT]
>  Tyto konstanty jsou implementovány modulem PDM verze 11.0 nebo novější. Nachází se v souboru activdbg100.h.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
typedef SCRIPT_ERROR_DEBUG_EXCEPTION_THROWN_KIND  
```  
  
## <a name="members"></a>Členové  
  
|Člen|Hodnota|Popis|  
|------------|-----------|-----------------|  
|ETK_FIRST_CHANCE|0x00000000|Tato výjimka je výjimka první příležitosti.|  
|ETK_USER_UNHANDLED|0x00000001|Tato výjimka není ošetřena v uživatelském kódu.|  
|ETK_UNHANDLED|0x00000002|Tato výjimka není ošetřena v kódu.|  
  
## <a name="see-also"></a>Viz také  
 [IActiveScriptErrorDebug110 – rozhraní](../../winscript/reference/iactivescripterrordebug110-interface.md)