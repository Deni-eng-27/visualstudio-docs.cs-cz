---
title: Tipy pro výkon | Microsoft Docs
ms.date: 9/11/2020
ms.topic: how-to
ms.assetid: 509d2d4f-48a5-4cdf-acad-6f7b75421303
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f260307b677046be54e6d80b0d8fe122b13292e4
ms.sourcegitcommit: 14637be49401f56341c93043eab560a4ff6b57f6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/14/2020
ms.locfileid: "90075467"
---
# <a name="perftips"></a>Tipy pro výkon

Ladicí program sady Visual Studio *tipy pro výkon* a integrovaný ladicí program **diagnostické nástroje** vám pomůžou monitorovat a analyzovat výkon aplikace při ladění.

I když diagnostické nástroje integrované v ladicím programu představují skvělý způsob, jak se dozvědět o problémech s výkonem při vývoji, může mít ladicí program významný dopad na výkon vaší aplikace. Pokud chcete shromažďovat přesnější data o výkonu, zvažte použití nástrojů v profileru výkonu jako další část šetření výkonu. Viz [spuštění nástrojů pro profilaci pomocí ladicího programu nebo bez něj](../profiling/running-profiling-tools-with-or-without-the-debugger.md).

## <a name="perftips"></a>Tipy pro výkon

Když ladicí program zastaví provádění na operaci zarážky nebo krokování, uplynulý čas mezi přerušením a předchozí zarážkou se zobrazí jako Tip v okně editoru. Další informace naleznete v tématu [tipy pro výkon: informace o výkonu při ladění v aplikaci Visual Studio](https://devblogs.microsoft.com/devops/perftips-performance-information-at-a-glance-while-debugging-with-visual-studio/).

![PerfTip](../profiling/media/dbgdiag_perf_perftip.png "DBGDIAG_PERF_PerfTip")

## <a name="diagnostics-tools-window"></a>Okno diagnostické nástroje

Zarážky a související časová data se zaznamenávají v okně **diagnostické nástroje** .

Následující obrázek znázorňuje okno **diagnostické nástroje** .

![DiagnosticTools&#45;-datum1](../profiling/media/diagnostictools-update1.png "DiagnosticTools-v-datum1")

- Časová osa **událostí přerušení** označuje zarážky, které byly dosaženy v relaci ladění. Kliknutím na událost můžete vybrat seznam podrobností **ladicího programu** .

- Graf **využití procesoru** zobrazuje změnu v využití CPU napříč všemi jádry procesoru v relaci ladění.

- Seznam **událostí** v podokně podrobností **ladicího programu** obsahuje položky pro každou událost přerušení.

- Sloupec **Trvání** události break zobrazuje uplynulý čas mezi událostí a předchozí zarážkou.

## <a name="turn-perftips-on-or-off"></a>Zapnout nebo vypnout tipy pro výkon

Povolení nebo zakázání tipy pro výkon:

1. V nabídce **ladění** vyberte **možnost možnosti**.

2. Zaškrtnutí nebo zrušení zaškrtnutí **Zobrazit uplynulý PerfTip při ladění**.

## <a name="turn-the-diagnostic-tools-window-on-or-off"></a>Zapnout nebo vypnout okno Diagnostické nástroje

Chcete-li povolit nebo zakázat okno Diagnostické nástroje:

1. V nabídce **ladění** vyberte **možnost možnosti**.

2. Zaškrtněte nebo zrušte zaškrtnutí políčka **Povolit diagnostické nástroje při ladění**.

## <a name="see-also"></a>Viz také

- [Profilace v sadě Visual Studio](../profiling/index.yml)
- [První seznámení s nástroji pro profilaci](../profiling/profiling-feature-tour.md)
