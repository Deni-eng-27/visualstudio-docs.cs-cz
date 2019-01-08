---
title: Profiler_script_type – výčet | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- PROFILER_SCRIPT_TYPE
apilocation:
- scrobj.dll
ms.assetid: 3ab6633a-6241-44f0-b837-14336f70c71e
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ac387af4601ff822982c10e61f9813b2db7e8047
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54086903"
---
# <a name="profilerscripttype-enumeration"></a>PROFILER_SCRIPT_TYPE – výčet
Určuje typ skriptu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
typedef enum {  
    PROFILER_SCRIPT_TYPE_USER,  
    PROFILER_SCRIPT_TYPE_DYNAMIC,  
    PROFILER_SCRIPT_TYPE_NATIVE,  
    PROFILER_SCRIPT_TYPE_DOM  
} PROFILER_SCRIPT_TYPE;  
```  
  
## <a name="members"></a>Členové  
  
|Člen|Popis|  
|------------|-----------------|  
|PROFILER_SCRIPT_TYPE_USER|Určuje skript uživatelem zapsaný kód.|  
|PROFILER_SCRIPT_TYPE_DYNAMIC|Určuje kód skriptu, který se vygeneruje dynamicky za běhu.|  
|PROFILER_SCRIPT_TYPE_NATIVE|Určuje typ skriptu pro nativní funkce a objekty, které jsou definovány skriptovací stroj.|  
|PROFILER_SCRIPT_TYPE_DOM|Určuje volání do Document Object Model (DOM) aplikace Internet Explorer, například volání `document.getElementById` metody.|  
  
## <a name="see-also"></a>Viz také  
 [Aktivních skriptů Profiler konstanty, výčty a struktury](../../winscript/reference/active-script-profiler-constants-enumerations-and-structures.md)   
 [IActiveScriptProfilerCallback::ScriptCompiled](../../winscript/reference/iactivescriptprofilercallback-scriptcompiled.md)   
 [IActiveScriptProfilerCallback2::OnFunctionEnterByName](../../winscript/reference/iactivescriptprofilercallback2-onfunctionenterbyname.md)   
 [IActiveScriptProfilerCallback2::OnFunctionExitByName](../../winscript/reference/iactivescriptprofilercallback2-onfunctionexitbyname.md)