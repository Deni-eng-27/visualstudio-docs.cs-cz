---
title: StopProfile | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- StopProfile
ms.assetid: be75b03c-7af5-4abe-a54a-6ee5479ad877
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 326ed9afa9d277babde5cda99ba5640f6d66bd98
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42676256"
---
# <a name="stopprofile"></a>StopProfile
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [StopProfile](https://docs.microsoft.com/visualstudio/profiling/stopprofile).  
  
`StopProfile` Funkce nastaví na hodnotu 0 (vypnuto) pro zadanou úroveň profilování čítač.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
PROFILE_COMMAND_STATUS PROFILERAPI StopProfile(  
                       PROFILE_CONTROL_LEVEL Level,   
                       unsigned int dwId);  
```  
  
#### <a name="parameters"></a>Parametry  
 `Level`  
  
 Informuje o úrovni profil, ke které výkonu shromažďování dat lze použít. Následující **PROFILE_CONTROL_LEVEL** enumerátory lze použít k označení jednu ze tří úrovní výkonu, které lze použít shromažďování dat:  
  
|Enumerátor|Popis|  
|----------------|-----------------|  
|PROFILE_GLOBALLEVEL|Globální nastavení úrovně má vliv na všechny procesy a vlákna při spuštění profilace.|  
|PROFILE_PROCESSLEVEL|Nastavení úrovně procesu mít vliv na všechna vlákna, které jsou součástí určeného procesu.|  
|PROFILE_THREADLEVEL|Vlákno profilace nastavení úrovně má vliv na zadaný podproces.|  
  
 `dwId`  
  
 Identifikátor procesu nebo vlákna generované systémem.  
  
## <a name="property-valuereturn-value"></a>Hodnota vlastnosti / návratová hodnota  
 Funkce označuje úspěch nebo neúspěch pomocí **PROFILE_COMMAND_STATUS** výčtu. Návratová hodnota může být jeden z následujících akcí:  
  
|Enumerátor|Popis|  
|----------------|-----------------|  
|PROFILE_ERROR_ID_NOEXIST|Profilace ID prvku neexistuje.|  
|PROFILE_ERROR_LEVEL_NOEXIST|Profilace Zadaná úroveň neexistuje.|  
|PROFILE_ERROR_MODE_NEVER|Režimu profilace byla nastavena na nikdy, když byla volána funkce.|  
|PROFILE_ERROR_NOT_YET_IMPLEMENTED|Profilace volání funkce, profilace úroveň nebo kombinací volání a úroveň není dosud implementována.|  
|PROFILE_OK|Volání bylo úspěšné.|  
  
## <a name="remarks"></a>Poznámky  
 StartProfile a StopProfile stav spuštění/zastavení profilování úrovně ovládacích prvků. Spustit/Zastavit výchozí hodnota je 1. Počáteční hodnotu můžete změnit v registru. Každé volání StartProfile nastaví operací spustit/zastavit na 1; každé volání StopProfile ji nastaví na hodnotu 0.  
  
 Při spuštění/zastavení je větší než 0, je stav operací spustit/zastavit na úrovni ON. Když je menší než nebo rovno 0, stav spuštění/zastavení je vypnuto.  
  
 Po spuštění/zastavení stavu a stavu pozastavení/obnovení se i na profilování stav úrovně je ON. Pro vlákno bude profilována, procesu globální, a úrovni stavy vláken pro vlákno musí být dále.  
  
## <a name="net-framework-equivalent"></a>Ekvivalent v rozhraní .NET Framework  
 Microsoft.VisualStudio.Profiler.dll  
  
## <a name="function-information"></a>Informace o funkci  
 Záhlaví: Deklarované v VSPerf.h  
  
 Knihovna importů: VSPerf.lib  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje metodu StopProfile. Příklad předpokládá, že volání metody StartProfile nebyly provedeny stejným vlákna nebo procesu identifikovaný [PROFILE_CURRENTID](../profiling/profile-currentid.md).  
  
```  
void ExerciseStopProfile()  
{  
    // StartProfile and StopProfile control the   
    // Start/Stop state for the profiling level.   
    // The default initial value of Start/Stop is 1.   
    // The initial value can be changed in the registry.   
    // Each call to StartProfile sets Start/Stop to 1;   
    // each call to StopProfile sets it to 0.   
  
    // Variables used to print output.  
    HRESULT hResult;  
    TCHAR tchBuffer[256];  
  
    // Declare enumeration to hold result of call  
    // to StopProfile.  
    PROFILE_COMMAND_STATUS profileResult;  
  
    profileResult = StopProfile(  
        PROFILE_THREADLEVEL,  
        PROFILE_CURRENTID);  
  
    // Format and print result.  
    LPCTSTR pszFormat = TEXT("%s %d.\0");  
    TCHAR* pszTxt = TEXT("StopProfile returned");  
    hResult = StringCchPrintf(tchBuffer, 256, pszFormat,   
        pszTxt, profileResult);  
  
#ifdef DEBUG  
    OutputDebugString(tchBuffer);  
#endif  
}  
```  
  
## <a name="see-also"></a>Viz také  
 [Reference k rozhraní API sady Visual Studio Profiler (nativní)](../profiling/visual-studio-profiler-api-reference-native.md)



