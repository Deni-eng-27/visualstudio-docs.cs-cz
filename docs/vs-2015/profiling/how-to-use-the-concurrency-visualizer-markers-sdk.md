---
title: 'Postupy: Použití sady SDK značek Vizualizátor souběžnosti | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 19a45032-f8a7-4137-890e-2ceeec938b8d
caps.latest.revision: 14
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 3df1139f34c17055703b1ffcbbe2711d5750b9a8
ms.sourcegitcommit: 2da366ba9ad124366f6502927ecc720985fc2f9e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68870052"
---
# <a name="how-to-use-the-concurrency-visualizer-markers-sdk"></a>Postupy: Použití SDK značek Vizualizéru souběžnosti

[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

V tomto tématu se dozvíte, jak použít sadu Vizualizátor souběžnosti SDK k vytváření rozsahů a zápisových příznaků, zpráv a výstrah.

### <a name="to-use-c"></a>Pro použitíC++

1. Přidejte do své aplikace podporu Vizualizátor souběžnosti sady SDK. Další informace najdete v tématu [sada Vizualizátor souběžnosti SDK](../profiling/concurrency-visualizer-sdk.md).

2. `include` Přidejte příkaz`using` a příkaz pro sadu SDK.

    ```cpp
    #include <cvmarkersobj.h>
    using namespace Concurrency::diagnostic;
    ```

3. Přidejte kód pro vytvoření tří rozsahů ve výchozí řadě značek a napište příznak, zprávu a výstrahu, jednu do každého rozpětí. Metody pro zápis příznaků, zpráv a výstrah jsou členy třídy [marker_series](../profiling/marker-series-class.md) . Konstruktor pro třídu [span](../profiling/span-class.md) vyžaduje `marker_series` objekt, aby každý rozsah byl přidružen ke konkrétní řadě značek. `span` Končí, když se odstraní.

    ```cpp
    marker_series series;
    span *flagSpan = new span(series, 1, _T("flag span"));
    series.write_flag(_T("Here is the flag."));
    delete flagSpan;

    span *messageSpan = new span(series, 2, _T("message span"));
    series.write_flag(_T("Here is the message."));
    delete messageSpan;

    span *alertSpan = new span(series, 3, _T("alert span"));
    series.write_flag(_T("Here is the alert."));
    delete alertSpan;
    ```

4. Na panelu nabídek vyberte možnost **analyzovat**, **Vizualizér souběžnosti**, **začněte s aktuálním projektem** a spusťte aplikaci a zobrazte Vizualizér souběžnosti. Následující ilustrace znázorňuje tři rozpětí a tři značky v Vizualizátor souběžnosti.

     ![Vizualizátor souběžnosti se 3 značkami a výstrahami](../profiling/media/cvmarkersnative.png "CvMarkersNative")

5. Přidejte kód pro vytvoření další vlastní řady značek voláním konstruktoru pro `marker_series` , který přebírá název řetězce pro řady značek.

    ```cpp
    marker_series flagSeries(_T("flag series"));
    span *flagSeriesSpan = new span(flagSeries, 1, _T("flag span"));
    flagSeries.write_flag(1, _T("flag"));
    // Sleep to even out the display in the Concurrency Visualizer.
    Sleep(50);
    delete flagSeriesSpan;

    marker_series messageSeries(_T("message series"));
    span *messageSeriesSpan = new span(messageSeries, 1, _T("message span"));
    messageSeries.write_message(1, _T("message"));
    // Sleep to even out the display in the Concurrency Visualizer.
    Sleep(50);
    delete messageSeriesSpan;
    ```

6. Spustí aktuální projekt, aby se zobrazil Vizualizér souběžnosti. Tato dvě série značek se zobrazí v zobrazení vláken v jejich vlastních koridorech. Následující ilustrace znázorňuje dvě nová rozpětí.

     ![Vizualizátor souběžnosti se 3 vlastními řadami značek](../profiling/media/cvmarkerseriesnative.png "CvMarkerSeriesNative")

### <a name="to-use-visual-basic-or-c"></a>Použití Visual Basic nebo C\#

1. Přidejte do své aplikace podporu Vizualizátor souběžnosti sady SDK. Další informace najdete v tématu [sada Vizualizátor souběžnosti SDK](../profiling/concurrency-visualizer-sdk.md).

2. Přidejte příkaz `Imports` nebo pro sadu SDK. `using`

    ```vb
    Imports Microsoft.ConcurrencyVisualizer.Instrumentation
    ```

    ```csharp
    using Microsoft.ConcurrencyVisualizer.Instrumentation;
    ```

3. Přidejte kód pro vytvoření tří různých rozsahů na výchozí řadě značek a napište příznak, zprávu a výstrahu, jednu do každého rozpětí. Objekt [span](/previous-versions/hh694189(v=vs.140)) vytvoříte voláním statické `EnterSpan` metody. Chcete-li zapisovat do výchozí řady, použijte statické metody zápisu třídy [značek](/previous-versions/hh694099(v=vs.140)) .

    ```vb
    Dim flagSpan As Span = Markers.EnterSpan("flag span")
    Markers.WriteFlag("Here is the flag.")
    flagSpan.Leave()

    Dim messageSpan As Span = Markers.EnterSpan("message span")
    ' Sleep for a millisecond to even out the display in the Concurrency Visualizer.
    System.Threading.Thread.Sleep(1)
    Markers.WriteMessage("Here is a message")
    messageSpan.Leave()

    Dim alertSpan As Span = Markers.EnterSpan("alert span")
    ' Sleep for a millisecond to even out the display in the Concurrency Visualizer.
    System.Threading.Thread.Sleep(1)
    Markers.WriteAlert("Here is an alert")
    alertSpan.Leave()
    ```

    ```csharp
    Span flagSpan = Markers.EnterSpan("flag span");
    Markers.WriteFlag("Here is the flag.");
    flagSpan.Leave();

    Span messageSpan = Markers.EnterSpan("message span");
    // Sleep for a millisecond to even out the display in the Concurrency Visualizer.
    System.Threading.Thread.Sleep(1);
    Markers.WriteMessage("Here is a message");
    messageSpan.Leave();

    Span alertSpan = Markers.EnterSpan("alert span");
    // Sleep for a millisecond to even out the display in the Concurrency Visualizer.
    System.Threading.Thread.Sleep(1);
    Markers.WriteAlert("Here is an alert");
    alertSpan.Leave();
    ```

4. Na panelu nabídek vyberte možnost **analyzovat**, **Vizualizér souběžnosti**, **začněte s aktuálním projektem** a spusťte aplikaci a zobrazte Vizualizér souběžnosti. Následující ilustrace znázorňuje tři rozpětí a tři značky v zobrazení vláken Vizualizátor souběžnosti.

     ![Vizualizátor souběžnosti se značkami a výstrahami](../profiling/media/cvmarkersmanaged.png "CvMarkersManaged")

5. Přidejte kód pro vytvoření řady značek zákazníka pomocí metody static [CreateMarkerSeries](/previous-versions/hh694171(v=vs.140)) . Třída [MarkerSeries](/previous-versions/hh694127(v=vs.140)) obsahuje metody pro vytváření a psaní příznaků, zpráv a upozornění.

    ```vb
    Dim flagSeries As MarkerSeries = Markers.DefaultWriter.CreateMarkerSeries("flag series")
    Dim flagSeriesSpan As Span = flagSeries.EnterSpan("flag span")
    System.Threading.Thread.Sleep(1)
    flagSeries.WriteFlag(1, "flag")
    System.Threading.Thread.Sleep(1)
    flagSeriesSpan.Leave()

    Dim messageSeries As MarkerSeries = Markers.DefaultWriter.CreateMarkerSeries("message series")
    Dim messageSeriesSpan As Span = messageSeries.EnterSpan("message span")
    messageSeries.WriteMessage("message")
    System.Threading.Thread.Sleep(1)
    messageSeriesSpan.Leave()
    ```

    ```csharp
    MarkerSeries flagSeries = Markers.DefaultWriter.CreateMarkerSeries("flag series");
    Span flagSeriesSpan = flagSeries.EnterSpan("flag span");
    System.Threading.Thread.Sleep(1);
    flagSeries.WriteFlag(1, "flag");
    System.Threading.Thread.Sleep(1);
    flagSeriesSpan.Leave();

    MarkerSeries messageSeries = Markers.DefaultWriter.CreateMarkerSeries("message series");
    Span messageSeriesSpan = messageSeries.EnterSpan("message span");
    messageSeries.WriteMessage("message");
    System.Threading.Thread.Sleep(1);
    messageSeriesSpan.Leave();
    ```

6. Spustí aktuální projekt, aby se zobrazil Vizualizér souběžnosti. Tři řady značek se zobrazí v zobrazení vláken v jejich vlastních koridorech. Následující ilustrace znázorňuje tři nové rozsahy.

     ![Vizualizátor souběžnosti se 3 vlastními řadami značek](../profiling/media/cvmarkerseriesmanaged.png "CvMarkerSeriesManaged")

## <a name="see-also"></a>Viz také

- [SDK Vizualizéru souběžnosti](../profiling/concurrency-visualizer-sdk.md)
