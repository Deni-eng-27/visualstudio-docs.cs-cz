---
title: CommentMarkProfile | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- CommentMarkProfile
- CommentMarkProfileA
ms.assetid: 33ccff45-c33a-4672-b41f-5b317b848cd1
caps.latest.revision: "11"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0cb46497c8e00cedeb4056571d8fa1d19eb26c0c
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="commentmarkprofile"></a>CommentMarkProfile
`CommentMarkProfile` Funkce vloží číselné značku a textového řetězce v souboru .vsp. Značky a komentáře, které má být vložen, profilace podprocesu, který obsahuje `CommentMarkProfile` funkce musí být ON.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
PROFILE_COMMAND_STATUS PROFILERAPI CommentMarkProfile(  
                                   long lMarker,   
                                   LPCTSTR szComment);  
```  
  
#### <a name="parameters"></a>Parametry  
 `lMarker`  
  
 Číselné značky pro vložení. Značky musí být větší než nebo rovno 0 (nula).  
  
 `szComment`  
  
 Ukazatel na textový řetězec k vložení. Řetězec musí být kratší než 256 znaků včetně ukončení hodnotu NULL.  
  
## <a name="property-valuereturn-value"></a>Hodnota vlastnosti / návratová hodnota  
 Funkce označuje úspěch či neúspěch pomocí **PROFILE_COMMAND_STATUS** výčtu. Vrácená hodnota může být jeden z následujících akcí:  
  
|Enumerátor|Popis|  
|----------------|-----------------|  
|MARK_ERROR_MARKER_RESERVED|Parametr je menší než nebo rovna 0. Tyto hodnoty jsou vyhrazené. Značky a komentáře nejsou popsané.|  
|MARK_ERROR_MODE_NEVER|Profilování režimu byl nastaven na nikdy, při volání funkce. Značky a komentáře nejsou popsané.|  
|MARK_ERROR_MODE_OFF|Profilování režimu byl nastaven na hodnotu OFF, při volání funkce. Značky a komentáře nejsou popsané.|  
|MARK_ERROR_NO_SUPPORT|Nepodporuje označit v tomto kontextu. Značky a komentáře nejsou popsané.|  
|MARK_ERROR_OUTOFMEMORY|Paměť nebyl k dispozici k zaznamenání události. Značky a komentáře nejsou popsané.|  
|MARK_TEXTTOOLONG|Řetězec překračuje maximální povolenou délku 256 znaků. Řetězec komentáře zkrácen a značky a komentáře se zaznamenávají.|  
|MARK_OK|MARK_OK je vrácen do indikuje úspěšné provedení.|  
  
## <a name="remarks"></a>Poznámky  
 Profilování stavu podprocesu, který obsahuje funkci profilu značky musí být v značky a komentáře vložit příkaz vsinstr – označit nebo s funkcí (CommentMarkAtProfile, CommentMarkProfile nebo MarkProfile).  
  
 Profil značky jsou globální v oboru. Například profil značka vložen do jedno vlákno slouží k označení počáteční nebo koncové segmentu dat v jakékoli vlákno v souboru .vsp.  
  
> [!IMPORTANT]
>  CommentMarkProfile metodu můžete použít jenom s instrumentace.  
  
## <a name="net-framework-equivalent"></a>Ekvivalent v rozhraní .NET Framework  
 Microsoft.VisualStudio.Profiler.dll  
  
## <a name="function-information"></a>Informace o funkci  
  
|||  
|-|-|  
|**Záhlaví**|Zahrnout VSPerf.h|  
|**Knihovna**|Použití VSPerf.lib|  
|**Kódování Unicode**|Implementovaná jako `CommentMarkProfileW` (Unicode) a `CommentMarkProfileA` (ANSI).|  
  
## <a name="example"></a>Příklad  
 Následující kód ukazuje volání funkce CommentMarkProfile. V příkladu se předpokládá použití Win32 řetězce makra a Unicode nastavení kompilátoru pro zjištění, zda kód volá [!INCLUDE[vcpransi](../profiling/includes/vcpransi_md.md)] volání funkce.  
  
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
 [Referenční dokumentace rozhraní API sady Visual Studio Profiler (nativní)](../profiling/visual-studio-profiler-api-reference-native.md)