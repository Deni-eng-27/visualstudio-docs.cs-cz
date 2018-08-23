---
title: Cvcreatedefaultmarkerseriesofdefaultprovider – funkce | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- cvmarkers/CvCreateDefaultMarkerSeriesOfDefaultProvider
helpviewer_keywords:
- CvCreateDefaultMarkerSeriesOfDefaultProvider method
ms.assetid: 24eb80f8-8fca-4c47-93b5-bb1eb8ffdffd
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4910a66481be1f00a0fd57e1a66c0756f11c6589
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42667210"
---
# <a name="cvcreatedefaultmarkerseriesofdefaultprovider-function"></a>CvCreateDefaultMarkerSeriesOfDefaultProvider – funkce
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [cvcreatedefaultmarkerseriesofdefaultprovider – funkce](https://docs.microsoft.com/visualstudio/profiling/cvcreatedefaultmarkerseriesofdefaultprovider-function).  
  
Vytvoří výchozí značky řady výchozího zprostředkovatele.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT CvCreateDefaultMarkerSeriesOfDefaultProvider(  
   _Out_ PCV_PROVIDER* ppProvider,  
   _Out_ PCV_MARKERSERIES* ppMarkerSeries  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ppProvider`  
 Adresa proměnné objektu zprostředkovatele. Adresa nesmí být NULL, proměnná může mít libovolnou hodnotu.  
  
 `ppMarkerSeries`  
 Adresa proměnné objektu značky řady. Adresa nesmí být NULL, proměnná může mít libovolnou hodnotu.  
  
## <a name="return-value"></a>Návratová hodnota  
 S_OK při řady zprostředkovatele a značky se úspěšně vytvořil nebo kód chyby v případě, že existuje byly všechny chyby. Použití makra SUCCEEDED nebo FAILED zkontrolujte chybovou podmínku.  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** cvmarkers.h  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace knihoven jazyka C++](../profiling/cpp-library-reference.md)



