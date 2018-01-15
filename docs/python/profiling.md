---
title: "Měření výkonu Python kódu v sadě Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 01/09/2018
ms.reviewer: 
ms.suite: 
ms.technology: devlang-python
ms.devlang: python
ms.tgt_pltfrm: 
ms.topic: article
caps.latest.revision: "1"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- python
- data-science
ms.openlocfilehash: bdfd378a9441aba9c57c56f1f853e5cdd27a8d49
ms.sourcegitcommit: 11740fed01cc602252ef698aaa11c07987b00570
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/12/2018
---
# <a name="profiling-python-code"></a>Profilace kódu jazyka Python

Visual Studio podporuje profilace aplikace Python, při použití překladače na základě CPython.

Spuštění profilování prostřednictvím **analyzovat > spuštění profilace Python** příkazu nabídky, otevře se dialogové okno konfigurace:

![Dialogové okno Konfigurace profilace](media/profiling-start.png)

Když vyberete **OK**, profileru spustí a otevře se sestava výkonu, pomocí nichž můžete prozkoumat, jak je čas strávený v aplikaci:

![Sestava profilace výkonu](media/profiling-results.png)

Ukázka, najdete v části video [profilace Python](https://mva.microsoft.com/en-US/training-courses/python-tools-for-visual-studio-2017-18121?l=s6FoC6LWE_1005918567) (Microsoft Virtual Academy, 3m00s).

> [!VIDEO https://mva.microsoft.com/en-US/training-courses-embed/python-tools-for-visual-studio-2017-18121/Video-Profiling-Python-s6FoC6LWE_1005918567]

## <a name="profiling-for-ironpython"></a>Profilace pro IronPython

Protože IronPython není základě CPython překladač, výše uvedené funkce profilování nefunguje.

Místo toho použijte sady Visual Studio .NET profileru spuštěním `ipy.exe` přímo jako cílová aplikace pomocí odpovídající argumenty spuštění spouštěcího skriptu. Zahrnout `-X:Debug` na příkazovém řádku, abyste ověřili, že všechny vaše Python můžete ladit kód a profilovaným. Tento argument vytváří sestavu výkonu včetně času stráveného v modulu runtime IronPython i vám kód. Váš kód je identifikovat za použití pozměnění názvy.

Alternativně IronPython má některé vlastní integrované profilace ale v současné době není žádný funkční vizualizér pro ni. V tématu [profileru IronPython](http://blogs.msdn.com/b/curth/archive/2009/03/29/an-ironpython-profiler.aspx) (Blogy MSDN) pro co je k dispozici.