---
title: Iactivescriptprofilercallback – rozhraní | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 76f9164b-b086-4b29-ac79-76f9c76f1d11
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e8f64f187638af7f9ab4bf6b80e88fe6992c78e6
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63386079"
---
# <a name="iactivescriptprofilercallback-interface"></a>IActiveScriptProfilerCallback – rozhraní
Poskytuje metody, které jsou používány skriptovací stroj objekt profileru upozornit, pokud dojde k událostem. Toto rozhraní je implementováno v objektu profileru.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IActiveScriptProfilerCallback::Initialize](../../winscript/reference/iactivescriptprofilercallback-initialize.md)|Volána k inicializaci objektu profileru pokaždé, když profilace je spuštěna na skriptovacím stroji.|  
|[IActiveScriptProfilerCallback::Shutdown](../../winscript/reference/iactivescriptprofilercallback-shutdown.md)|Volá se, aby zdarma a uvolnění objektu profileru pokaždé, když je profilování zastaveno na skriptovacím stroji.|  
|[IActiveScriptProfilerCallback::ScriptCompiled](../../winscript/reference/iactivescriptprofilercallback-scriptcompiled.md)|Profiler upozorní, že objekt, který skriptovací modul kompilaci skriptu.|  
|[IActiveScriptProfilerCallback::FunctionCompiled](../../winscript/reference/iactivescriptprofilercallback-functioncompiled.md)|Profiler upozorní, že při kompilaci skriptu, který skriptovací modul narazil na funkci.|  
|[IActiveScriptProfilerCallback::OnFunctionEnter](../../winscript/reference/iactivescriptprofilercallback-onfunctionenter.md)|Upozorní objekt profileru, který skriptovací stroj je před spuštěním volání funkce, která není volání do modelu Document Object Model (DOM).|  
|[IActiveScriptProfilerCallback::OnFunctionExit](../../winscript/reference/iactivescriptprofilercallback-onfunctionexit.md)|Profiler upozorní, že objekt, dokončení provádění funkce skriptovací stroj volání, které není volání do modelu DOM.|  
  
## <a name="remarks"></a>Poznámky  
 Oznámení o volání funkce do modelu Document Object Model (DOM) poskytuje [iactivescriptprofilercallback2 – rozhraní](../../winscript/reference/iactivescriptprofilercallback2-interface.md).  
  
> [!NOTE]
> Chcete-li přidat možnost spuštění a zastavení profilování při spuštění skriptu, volání těchto metod. Pomocí těchto metod můžete získat úplný zásobník volání, pokud [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] je spuštěna při spuštění nebo zastavení profilování.  
> 
> - Volání [IActiveScriptProfilerControl2::CompleteProfilerStart](../../winscript/reference/iactivescriptprofilercontrol2-completeprofilerstart.md) pro oznámení profileru, které jste spustili profilace.  
>   - Volání [IActiveScriptProfilerControl2::PrepareProfilerStop](../../winscript/reference/iactivescriptprofilercontrol2-prepareprofilerstop.md) pro oznámení profileru, že vám brzy ukončí profilaci.  
  
## <a name="see-also"></a>Viz také  
 [Rozhraní profileru aktivních skriptů](../../winscript/reference/active-script-profiler-interfaces.md)