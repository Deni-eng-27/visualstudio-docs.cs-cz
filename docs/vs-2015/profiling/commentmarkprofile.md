---
title: CommentMarkProfile | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- CommentMarkProfile
- CommentMarkProfileA
ms.assetid: 33ccff45-c33a-4672-b41f-5b317b848cd1
caps.latest.revision: 16
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 750ce3cbcae593aee315998ec8b205a71e004d41
ms.sourcegitcommit: b885f26e015d03eafe7c885040644a52bb071fae
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/30/2020
ms.locfileid: "85543040"
---
# <a name="commentmarkprofile"></a>CommentMarkProfile
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

`CommentMarkProfile`Funkce vloží číselnou značku a textový řetězec do souboru. vsp. Pro značku a komentář, které mají být vloženy, musí být profilování vlákna, které obsahuje `CommentMarkProfile` funkci, Zapnuto.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
PROFILE_COMMAND_STATUS PROFILERAPI CommentMarkProfile(  
                                   long lMarker,   
                                   LPCTSTR szComment);  
```  
  
#### <a name="parameters"></a>Parametry  
 `lMarker`  
  
 Číselná značka, která se má vložit Značka musí být větší než nebo rovna 0 (nula).  
  
 `szComment`  
  
 Ukazatel na textový řetězec, který chcete vložit. Řetězec musí být kratší než 256 znaků, včetně ukončovacího znaku NULL.  
  
## <a name="property-valuereturn-value"></a>Hodnota vlastnosti / návratová hodnota  
 Funkce označuje úspěch nebo neúspěch pomocí **PROFILE_COMMAND_STATUS** výčtu. Návratová hodnota může být jedna z následujících:  
  
|Čítače|Popis|  
|----------------|-----------------|  
|MARK_ERROR_MARKER_RESERVED|Parametr je menší nebo roven 0. Tyto hodnoty jsou rezervované. Značka a komentář nejsou zaznamenávány.|  
|MARK_ERROR_MODE_NEVER|Režim profilace byl nastaven na hodnotu nikdy při volání funkce. Značka a komentář nejsou zaznamenávány.|  
|MARK_ERROR_MODE_OFF|Režim profilace byl nastaven na hodnotu OFF při volání funkce. Značka a komentář nejsou zaznamenávány.|  
|MARK_ERROR_NO_SUPPORT|V tomto kontextu není podporována žádná podpora značek. Značka a komentář nejsou zaznamenávány.|  
|MARK_ERROR_OUTOFMEMORY|Paměť nebyla k dispozici pro záznam události. Značka a komentář nejsou zaznamenávány.|  
|MARK_TEXTTOOLONG|Řetězec překračuje maximální 256 znaků. Řetězec komentáře je zkrácen a je zaznamenána značka a komentář.|  
|MARK_OK|MARK_OK je vráceno pro indikaci úspěchu.|  
  
## <a name="remarks"></a>Poznámky  
 Stav profilace vlákna obsahujícího profil značky musí být zapnutý, pokud jsou značky a komentáře vložené pomocí příkazu VSInstr Mark nebo with Functions (CommentMarkAtProfile, CommentMarkProfile nebo MarkProfile).  
  
 Značky profilu jsou v oboru globální. Například značka Profile vložená v jednom vlákně může být použita k označení začátku nebo konce datového segmentu v jakémkoli vlákně v souboru. vsp.  
  
> [!IMPORTANT]
> Metodu CommentMarkProfile lze použít pouze s instrumentací.  
  
## <a name="net-framework-equivalent"></a>Ekvivalent v rozhraní .NET Framework  
 Microsoft.VisualStudio.Profiler.dll  
  
## <a name="function-information"></a>Informace o funkci  
  
|Položka|Hodnota|  
|-|-|  
|**Hlaviček**|Zahrnout VSPerf. h|  
|**Knihovna**|Použití VSPerf. lib|  
|**Kódování Unicode**|Implementováno jako `CommentMarkProfileW` (Unicode) a `CommentMarkProfileA` (ANSI).|  
  
## <a name="example"></a>Příklad  
 Následující kód ilustruje volání funkce CommentMarkProfile. Příklad předpokládá použití maker řetězců Win32 a nastavení kompilátoru Unicode k určení, zda kód volá [!INCLUDE[vcpransi](../includes/vcpransi-md.md)] volání funkce.  
  
```  
void ExerciseCommentMarkProfile()  
{  
    // Declare and initalize variables to pass to   
    // CommentMarkProfile.  The values of these   
    // parameters are assigned based on the needs   
    // of the code; and for the sake of simplicity  
    // in this example, the variables are assigned  
    // arbitrary values.  
    long markId = 01;  
    TCHAR * markText = TEXT("Exercising CommentMarkProfile...");  
  
    // Variables used to print output.  
    HRESULT hResult;  
    TCHAR tchBuffer[256];  
  
    // Declare MarkOperationResult Enumerator.    
    // Holds return value from call to CommentMarkProfile.  
    PROFILE_COMMAND_STATUS markResult;  
  
    markResult = CommentMarkProfile(  
        markId,  
        markText);  
  
    // Format and print result.  
    LPCTSTR pszFormat = TEXT("%s %d.\0");  
    TCHAR* pszTxt = TEXT("CommentMarkProfile returned");  
    hResult = StringCchPrintf(tchBuffer, 256, pszFormat,   
        pszTxt, markResult);  
  
#ifdef DEBUG  
    OutputDebugString(tchBuffer);  
#endif  
}  
```  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace rozhraní API pro Visual Studio Profiler (nativní)](../profiling/visual-studio-profiler-api-reference-native.md)
