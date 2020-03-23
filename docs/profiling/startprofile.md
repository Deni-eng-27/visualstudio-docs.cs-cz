---
title: StartProfile | Dokumenty společnosti Microsoft
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- StartProfile
ms.assetid: 1761311d-c9d5-48f5-b1f8-b3605829940a
author: mikejo5000
ms.author: mikejo
manager: jillfra
monikerRange: vs-2017
ms.workload:
- multiple
ms.openlocfilehash: 9ff4b4973bff395cea6b73219a2098543ee6819e
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2020
ms.locfileid: "74778255"
---
# <a name="startprofile"></a>StartProfile
Funkce `StartProfile` nastaví čítač na 1 (zapnuto) pro zadanou úroveň profilování.

## <a name="syntax"></a>Syntaxe

```cpp
PROFILE_COMMAND_STATUS PROFILERAPI StartProfile(
                        PROFILE_CONTROL_LEVEL Level,
                        unsigned int dwId);
```

#### <a name="parameters"></a>Parametry
 `Level`

 Označuje úroveň profilu, na kterou lze použít shromažďování dat o výkonu. Následující **PROFILE_CONTROL_LEVEL** čítače výčtu lze použít k označení jedné ze tří úrovní, na které lze použít shromažďování dat výkonu:

|Čítač výčtu|Popis|
|----------------|-----------------|
|PROFILE_GLOBALLEVEL|Nastavení globální úrovně ovlivňuje všechny procesy a vlákna v profilování spustit.|
|PROFILE_PROCESSLEVEL|Nastavení úrovně procesu ovlivní všechna vlákna, která jsou součástí zadaného procesu.|
|PROFILE_THREADLEVEL|Nastavení úrovně profilování vláken ovlivňuje zadané vlákno.|

 `dwId`

 Identifikátor procesu nebo vlákna generovaný systémem.

## <a name="property-valuereturn-value"></a>Hodnota/vrácená hodnota nemovitosti
 Funkce označuje úspěch nebo neúspěch pomocí **PROFILE_COMMAND_STATUS** výčtu. Vrácená hodnota může být jedna z následujících hodnot:

|Čítač výčtu|Popis|
|----------------|-----------------|
|PROFILE_ERROR_ID_NOEXIST|ID prvku profilování neexistuje.|
|PROFILE_ERROR_LEVEL_NOEXIST|Zadaná úroveň profilování neexistuje.|
|PROFILE_ERROR_MODE_NEVER|Režim profilování byl nastaven na NIKDY, když byla volána funkce.|
|PROFILE_ERROR_NOT_YET_IMPLEMENTED|Profilování volání funkce, profilování úroveň nebo kombinace volání a úroveň ještě není implementována.|
|PROFILE_OK|Volání bylo úspěšné.|

## <a name="remarks"></a>Poznámky
 StartProfile a StopProfile řídí stav Start/Stop pro úroveň profilování. Výchozí hodnota Start/Stop je 1. Počáteční hodnotu lze změnit v registru. Každé volání StartProfile nastaví Start/Stop na 1; každé volání StopProfile nastaví na 0.

 Pokud je start/stop větší než 0, stav Start/Stop pro úroveň je ZAPNUTO. Pokud je menší než nebo rovno 0, stav Start/Stop je vypnutý.

 Když jsou stav Start/Stop a Stav Pozastavení/Obnovení zapnuty, stav profilování pro úroveň je zapnuto. Aby bylo vlákno profilováno, musí být globální stavy úrovně procesu a vlákna pro vlákno zapnuty.

## <a name="net-framework-equivalent"></a>Ekvivalent rozhraní .NET Framework
 *Soubor Microsoft.VisualStudio.Profiler.dll*

## <a name="function-information"></a>Informace o funkci
 Záhlaví: Deklarováno v *VSPerf.h*

 Knihovna importu: *VSPerf.lib*

## <a name="example"></a>Příklad
 Následující příklad ilustruje volání funkce StartProfile.

```cpp
void ExerciseStartProfile()
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

    // Declare enumeration to hold return value of
    // the call to StartProfile.
    PROFILE_COMMAND_STATUS profileResult;

    profileResult = StartProfile(
        PROFILE_THREADLEVEL,
        PROFILE_CURRENTID);

    // Format and print result.
    LPCTSTR pszFormat = TEXT("%s %d.\0");
    TCHAR* pszTxt = TEXT("StartProfile returned");
    hResult = StringCchPrintf(tchBuffer, 256, pszFormat,
        pszTxt, profileResult);

#ifdef DEBUG
    OutputDebugString(tchBuffer);
#endif
}
```

## <a name="see-also"></a>Viz také
- [Odkaz na rozhraní API profileru sady Visual Studio (nativní)](../profiling/visual-studio-profiler-api-reference-native.md)
