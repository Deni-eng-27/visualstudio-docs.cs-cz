---
title: Cvcreatedefaultmarkerseriesofdefaultprovider – funkce | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- cvmarkers/CvCreateDefaultMarkerSeriesOfDefaultProvider
helpviewer_keywords:
- CvCreateDefaultMarkerSeriesOfDefaultProvider method
ms.assetid: 24eb80f8-8fca-4c47-93b5-bb1eb8ffdffd
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e50e0d109ac5cfd17c5913213c4b86b406927593
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53967651"
---
# <a name="cvcreatedefaultmarkerseriesofdefaultprovider-function"></a>Cvcreatedefaultmarkerseriesofdefaultprovider – funkce
Vytvoří výchozí značky řady výchozího zprostředkovatele.  
  
## <a name="syntax"></a>Syntaxe  
  
```C  
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
 **Záhlaví:** *cvmarkers.h*  
  
## <a name="see-also"></a>Viz také:  
 [Referenční dokumentace knihoven jazyka C++](../profiling/cpp-library-reference.md)