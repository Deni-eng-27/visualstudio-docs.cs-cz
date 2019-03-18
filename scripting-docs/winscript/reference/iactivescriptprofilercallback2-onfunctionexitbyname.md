---
title: IActiveScriptProfilerCallback2::OnFunctionExitByName | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IActiveScriptProfilerCallback2::OnFunctionExitByName
ms.assetid: a6ddead4-e66d-4789-b778-84e5c343f908
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 87f0b7e7a3cea4e3e59fb43ef9ddc2d4934552e6
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58146562"
---
# <a name="iactivescriptprofilercallback2onfunctionexitbyname"></a>IActiveScriptProfilerCallback2::OnFunctionExitByName
Profiler upozorní, že objekt, který skriptovací modul dokončení volání funkce Document Object Model (DOM).  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT OnFunctionExitByName(  
    [in] [string] const WCHAR *pwszFunctionName,  
    [in] PROFILER_SCRIPT_TYPE scriptType);  
  
```  
  
#### <a name="parameters"></a>Parametry  
 `pwszFunctionName`  
 [in] Název funkce skriptovací stroj ukončen.  
  
 `scriptType`  
 [in] Typ funkce. Popis platných hodnot naleznete v tématu [profiler_script_type – výčet](../../winscript/reference/profiler-script-type-enumeration.md).  
  
## <a name="return-value"></a>Návratová hodnota  
 Skriptovací modul se ignoruje vrácenou hodnotu této metody.  
  
## <a name="remarks"></a>Poznámky  
 Pro volání modelu DOM, skriptovací stroj volá tuto metodu, bez volání [IActiveScriptProfilerCallback::OnFunctionExit](../../winscript/reference/iactivescriptprofilercallback-onfunctionexit.md). Je to z důvodu velkého počtu jedinečných metody a vlastnosti v modelu DOM.  
  
## <a name="see-also"></a>Viz také  
 [IActiveScriptProfilerCallback2::OnFunctionEnterByName](../../winscript/reference/iactivescriptprofilercallback2-onfunctionenterbyname.md)   
 [IActiveScriptProfilerCallback2 – rozhraní](../../winscript/reference/iactivescriptprofilercallback2-interface.md)