---
title: StartTrackingContextWithRoot | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- StartTrackingContextWithRoot
apilocation:
- filetracker.dll
apitype: COM
helpviewer_keywords:
- StartTrackingContextWithRoot
ms.assetid: f6ef2b76-8035-4a14-8195-aa221c46ef48
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 1844901da84c91cc35df18c9867897c634705a39
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/09/2018
---
# <a name="starttrackingcontextwithroot"></a>StartTrackingContextWithRoot
Spustí kontextu sledování pomocí souboru odpovědí zadání kořenovou značku.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp 
HRESULT WINAPI StartTrackingContextWithRoot(LPCTSTR intermediateDirectory, LPCTSTR taskName, LPCTSTR rootMarkerResponseFile);  
```  
  
#### <a name="parameters"></a>Parametry  
 [in] `intermediateDirectory`  
 Adresář, do které chcete uložit protokol sledování.  
  
 [in] `taskName`  
 Identifikuje kontext sledování. Tento název se používá k vytvoření názvu souboru protokolu.  
  
 [in] `rootMarkerResponseFile`  
 Cesta souboru odpovědí, který obsahuje kořenovou značku. Název kořenového slouží k seskupení všech sledování pro kontext, společně.  
  
## <a name="return-value"></a>Návratová hodnota  
 **HRESULT** s **úspěšné** nastaven bit, pokud kontext sledování se vytvořil.  
  
## <a name="requirements"></a>Požadavky  
 **Header:** FileTracker.h  
  
## <a name="see-also"></a>Viz také  
 [StartTrackingContext](../msbuild/starttrackingcontext.md)