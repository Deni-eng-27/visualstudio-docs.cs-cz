---
title: WriteAllTLogs | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: msbuild
ms.topic: conceptual
api_name:
- WriteAllTLogs
api_location:
- filetracker.dll
api_type:
- COM
helpviewer_keywords:
- WriteAllTLogs
ms.assetid: 1fa3e10b-263c-4960-a9ad-485c02a7a872
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 371357249bb9674a636859c995ad076eb41c2a08
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/17/2019
ms.locfileid: "59656424"
---
# <a name="writealltlogs"></a>WriteAllTLogs
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Zapisuje protokoly sledování pro všechna vlákna a kontext.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT WINAPI WriteAllTLogs(LPCTSTR intermediateDirectory, LPCTSTR tlogRootName);  
```  
  
#### <a name="parameters"></a>Parametry  
 [in] `intermediateDirectory`  
 Adresáře, ve kterém k uložení protokolu sledování.  
  
 [in] `tlogRootName`  
 Název kořenového názvu souboru protokolu.  
  
## <a name="return-value"></a>Návratová hodnota  
 [HRESULT] ()<!-- TODO: review code entity reference <xref:assetId:///HRESULT?qualifyHint=False&amp;autoUpgrade=True>  -->) s ([úspěch]<!-- TODO: review code entity reference <xref:assetId:///SUCCEEDED?qualifyHint=False&amp;autoUpgrade=True>  -->) sadu bitů, pokud byl vytvořen kontext sledování.  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** FileTracker.h  
  
## <a name="see-also"></a>Viz také  
 [WriteContextTLogs](../msbuild/writecontexttlogs.md)
