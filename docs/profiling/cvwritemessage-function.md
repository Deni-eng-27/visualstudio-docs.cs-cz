---
title: Funkce Cvwritemessage – | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- cvmarkers/CvWriteMessageW
- cvmarkers/CvWriteMessageExW
- cvmarkers/CvWriteMessageVA
- cvmarkers/CvWriteMessageExVW
- cvmarkers/CvWriteMessageExA
- cvmarkers/CvWriteMessageA
- cvmarkers/CvWriteMessageExVA
- cvmarkers/CvWriteMessageVW
helpviewer_keywords:
- CvWriteMessageExVA method
- CvWriteMessageW method
- CvWriteMessageVW method
- CvWriteMessageExVW method
- CvWriteMessageExW method
- CvWriteMessageA method
- CvWriteMessageVA method
- CvWriteMessageExA method
ms.assetid: e20ae7be-bfa7-437a-b8c1-fa0f1baa7f83
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 66fb584090a0b6483c18f8254eb4a96b6186d51e
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "85332125"
---
# <a name="cvwritemessage-function"></a>Cvwritemessage – – funkce
Zapíše zprávu do trasovacího souboru Vizualizátor souběžnosti.

## <a name="syntax"></a>Syntaxe

```C
HRESULT CvWriteMessageW(
    _In_reads_bytes_(16) PCV_MARKERSERIES pMarkerSeries,
    _In_ PCWSTR pMessage,
    ...
    );

HRESULT CvWriteMessageA(
    PCV_MARKERSERIES pMarkerSeries,
    _In_ PCSTR pMessage,
    ...
    );

HRESULT CvWriteMessageVW(
    _In_reads_bytes_(16) PCV_MARKERSERIES pMarkerSeries,
    _In_ PCWSTR pMessage,
    _In_ va_list argList);

HRESULT CvWriteMessageVA(
    _In_reads_bytes_(16) PCV_MARKERSERIES pMarkerSeries,
    _In_ PCSTR pMessage,
    _In_ va_list argList);

HRESULT CvWriteMessageExW(
    _In_reads_bytes_(16) PCV_MARKERSERIES pMarkerSeries,
    _In_ CV_IMPORTANCE level,
    _In_ int category,
    _In_ PCWSTR pMessage,
    ...
    );

HRESULT CvWriteMessageExA(
    _In_reads_bytes_(16) PCV_MARKERSERIES pMarkerSeries,
    _In_ CV_IMPORTANCE level,
    _In_ int category,
    _In_ PCSTR pMessage,
    ...
    );

HRESULT CvWriteMessageExVW(
    _In_reads_bytes_(16) PCV_MARKERSERIES pMarkerSeries,
    _In_ CV_IMPORTANCE level,
    _In_ int category,
    _In_ PCWSTR pMessage,
    _In_ va_list argList);

HRESULT CvWriteMessageExVA(
    _In_reads_bytes_(16) PCV_MARKERSERIES pMarkerSeries,
    _In_ CV_IMPORTANCE level,
    _In_ int category,
    _In_ PCSTR pMessage,
    _In_ va_list argList);
```

#### <a name="parameters"></a>Parametry
 `argList` Seznam argumentů

 `category` Kategorie rozsahu

 `level` Úroveň důležitosti rozpětí.

 `pMarkerSeries` Platný kontext řady značek Nemůže mít hodnotu NULL.

 `pMessage` Řetězec formátu zprávy Nemůže mít hodnotu NULL.

## <a name="return-value"></a>Vrácená hodnota
 S_OK při úspěšném zápisu zprávy Kód chyby v případě, že došlo k chybám. Ke kontrole chybového stavu použijte makra SUCCEEDED nebo FAILed.

## <a name="requirements"></a>Požadavky
 **Záhlaví:** *cvmarkers. h*

 **Kódování Unicode:** CvWriteMessageW, CvWriteMessageVW, CvWriteMessageExW, CvWriteMessageExVW

 **ANSI:** CvWriteMessageA, CvWriteMessageVA, CvWriteMessageExA, CvWriteMessageExVA

## <a name="see-also"></a>Viz také
- [Referenční dokumentace knihovny C++](../profiling/cpp-library-reference.md)