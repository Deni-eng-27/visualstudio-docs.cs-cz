---
title: Měření výkonu kód Python
description: Jak používat Visual Studio profiler zkontrolovat výkon jazyka Python kódu, kdy usnig na základě CPython překladače.
ms.date: 01/09/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: 2f0bd25221f975cd8df122af51af20d125a43a65
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
ms.locfileid: "31584071"
---
# <a name="profiling-python-code"></a>Profilace kódu jazyka Python

Při použití překladače na základě CPython, můžete profil aplikace Python. (Viz [funkce matice – profilace](overview-of-python-tools-for-visual-studio.md#matrix-profiling) dostupnosti této funkce pro různé verze sady Visual Studio.)

Spuštění profilování prostřednictvím **analyzovat > spuštění profilace Python** příkazu nabídky, otevře se dialogové okno konfigurace:

![Dialogové okno Konfigurace profilace](media/profiling-start.png)

Když vyberete **OK**, profileru spustí a otevře se sestava výkonu, pomocí nichž můžete prozkoumat, jak je čas strávený v aplikaci:

![Sestava profilace výkonu](media/profiling-results.png)

|   |   |
|---|---|
| ![film ikonu fotoaparátu pro video](../install/media/video-icon.png "přehrát video") | [Podívejte se na video (Microsoft Virtual Academy)](https://mva.microsoft.com/en-US/training-courses-embed/python-tools-for-visual-studio-2017-18121/Video-Profiling-Python-s6FoC6LWE_1005918567) pro předvedení Python profilace (3 m 00s).|

> [!Note]
> V současné době podporuje pouze tato úroveň profilace aplikací úplné sadě Visual Studio, ale určitě chceme slyšet váš názor na funkce. Použití [ **váš názor produktu** tlačítko](#feedback) v dolní části této stránky.

## <a name="profiling-for-ironpython"></a>Profilace pro IronPython

Protože IronPython není základě CPython překladač, výše uvedené funkce profilování nefunguje.

Místo toho použijte sady Visual Studio .NET profileru spuštěním `ipy.exe` přímo jako cílová aplikace pomocí odpovídající argumenty spuštění spouštěcího skriptu. Zahrnout `-X:Debug` na příkazovém řádku, abyste ověřili, že všechny vaše Python můžete ladit kód a profilovaným. Tento argument vytváří sestavu výkonu včetně času stráveného v modulu runtime IronPython i vám kód. Váš kód je identifikovat za použití pozměnění názvy.

Alternativně IronPython má některé vlastní integrované profilace ale v současné době není žádný funkční vizualizér pro ni. V tématu [profileru IronPython](http://blogs.msdn.com/b/curth/archive/2009/03/29/an-ironpython-profiler.aspx) (Blogy MSDN) pro co je k dispozici.