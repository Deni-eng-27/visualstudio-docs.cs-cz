---
title: DA0008-počet shromážděných ukázek | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.performance.rules.DATooFewSamples
- vs.performance.8
- vs.performance.DA0008
- vs.performance.rules.DA0008
ms.assetid: 8a5b78aa-7b3d-476c-a47d-abfaff3fae7c
author: mikejo5000
ms.author: mikejo
manager: jillfra
monikerRange: vs-2017
ms.workload:
- multiple
ms.openlocfilehash: 5dd1114f4be0ed943c9a582c04d9917b03ca75c3
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "85520780"
---
# <a name="da0008-few-samples-collected"></a>DA0008: Shromážděno málo vzorků

|Položka|Hodnota|
|-|-|
|ID pravidla|DA0008|
|Kategorie|Využití Nástroje pro profilaci|
|Metoda profilace|Vzorkování|
|Zpráva|Bylo shromážděno pouze několik ukázek. Zvažte delší spuštění nebo rychlejší vzorkovací frekvenci pro důležitější výsledky.|
|Typ pravidla|Informace|

## <a name="cause"></a>Příčina
 Při spuštění profilace bylo shromážděno pouze několik ukázek.

## <a name="rule-description"></a>Popis pravidla
 Při použití metody vzorkování byste měli shromáždit statisticky významný počet vzorků, abyste se ujistili, že data představují skutečné chování programu. Chcete-li minimalizovat chyby vzorkování, měli byste se pokusit shromáždit alespoň 1000 vzorků chování při spuštění instrukcí programu. Pokud neshromáždíte dostatek ukázek, můžete při analýze dat profilace být zauváděna do kódu.

## <a name="how-to-fix-violations"></a>Jak opravit porušení
 Vezměte v úvahu profilaci delšího spuštění aplikace nebo pomocí rychlejšího vzorkovacího kurzu Získejte statisticky významné výsledky. Informace o tom, jak změnit vzorkovací frekvenci v integrovaném vývojovém prostředí sady Visual Studio, naleznete v tématu [How to: zvolit události vzorkování](../profiling/how-to-choose-sampling-events.md). Další informace o tom, jak změnit vzorkovací frekvenci při použití příkazového řádku Nástroje pro profilaci, najdete v tématu [Timer](../profiling/timer.md) v odkazu [VSPerfCmd](../profiling/vsperfcmd.md) .
