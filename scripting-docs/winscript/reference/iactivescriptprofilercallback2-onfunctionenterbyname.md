---
title: IActiveScriptProfilerCallback2::OnFunctionEnterByName | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IActiveScriptProfilerCallback2::OnFunctionEnterByName
ms.assetid: 24b1593a-97fc-4d70-9b85-ec86fb59f987
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f6fdb4addace1b0bbabdd4303c3943b976763514
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58146094"
---
# <a name="iactivescriptprofilercallback2onfunctionenterbyname"></a>IActiveScriptProfilerCallback2::OnFunctionEnterByName
Upozorní objekt profileru, který je skriptovací stroj se to provést volání funkce Document Object Model (DOM).  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT OnFunctionEnterByName(  
    [in] [string] const WCHAR *pwszFunctionName,  
    [in] PROFILER_SCRIPT_TYPE scriptType);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pwszFunctionName`  
 [in] Název funkce, která skriptovací stroj se to provést.  
  
 `scriptType`  
 [in] Typ funkce. Popis platných hodnot naleznete v tématu [profiler_script_type – výčet](../../winscript/reference/profiler-script-type-enumeration.md).  
  
## <a name="return-value"></a>Návratová hodnota  
 Skriptovací modul se ignoruje vrácenou hodnotu této metody.  
  
## <a name="remarks"></a>Poznámky  
 Pro volání modelu DOM, skriptovací stroj volá tuto metodu, bez volání [IActiveScriptProfilerCallback::OnFunctionEnter](../../winscript/reference/iactivescriptprofilercallback-onfunctionenter.md). Je to z důvodu velkého počtu jedinečných metody a vlastnosti v modelu DOM.  
  
## <a name="see-also"></a>Viz také  
 [IActiveScriptProfilerCallback2::OnFunctionExitByName](../../winscript/reference/iactivescriptprofilercallback2-onfunctionexitbyname.md)   
 [IActiveScriptProfilerCallback2 – rozhraní](../../winscript/reference/iactivescriptprofilercallback2-interface.md)