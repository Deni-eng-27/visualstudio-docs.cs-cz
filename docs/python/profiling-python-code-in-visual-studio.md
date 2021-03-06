---
title: Měření výkonu kódu Pythonu
description: Pomocí profileru sady Visual Studio můžete kontrolovat výkon kódu Pythonu při použití překladačů založených na CPython.
ms.date: 11/12/2018
ms.topic: how-to
author: JoshuaPartlow
ms.author: joshuapa
manager: jillfra
ms.custom: seodec18
ms.workload:
- python
- data-science
ms.openlocfilehash: bf10a1f4474c2916cd63402eac487af7545b0f8f
ms.sourcegitcommit: 566144d59c376474c09bbb55164c01d70f4b621c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/19/2020
ms.locfileid: "90810663"
---
# <a name="profile-python-code"></a>Profil kódu Pythonu

Při použití překladačů založeného na CPython můžete profilovat aplikaci v Pythonu. (Další informace najdete v tématu [funkce – profilace matice](overview-of-python-tools-for-visual-studio.md#matrix-profiling) pro dostupnost této funkce pro různé verze sady Visual Studio.)

## <a name="profiling-for-cpython-based-interpreters"></a>Profilace pro interprety založené na CPython

Profilování se spouští příkazem nabídky **analyzovat**  >  **spuštění v Pythonu** , který otevře dialogové okno Konfigurace:

![Dialog konfigurace profilace](media/profiling-start.png)

Když vyberete **OK**, Profiler se spustí a otevře se sestava o výkonu, pomocí které můžete prozkoumat dobu strávenou v aplikaci:

![Sestava o výkonu profilace](media/profiling-results.png)

> [!Note]
> V současné době aplikace Visual Studio podporuje pouze tuto úroveň profilování kompletních aplikací, ale určitě chceme slyšet váš názor na budoucí možnosti. V dolní části této stránky použijte tlačítko **Zpětná vazba produktu** .

## <a name="profiling-for-ironpython"></a>Profilace pro Ironpythonu

Vzhledem k tomu, že Ironpythonu není Interpret založený na CPython, funkce profilování výše nefunguje.

Místo toho použijte Visual Studio .NET Profiler tak, že spustíte *ipy.exe* přímo jako cílovou aplikaci, pomocí příslušných argumentů spusťte spouštěcí skript. Zahrňte do `-X:Debug` příkazového řádku, abyste měli jistotu, že se dá ladit a profilovat celý kód Pythonu. Tento argument generuje sestavu o výkonu, včetně času stráveného v modulu runtime Ironpythonu i ve vašem kódu. Váš kód je identifikován pomocí pozměněných názvů.

Ironpythonu má některé vlastní integrované profilování, ale pro něj zatím neexistuje žádný dobrý Vizualizér. Co je k dispozici, najdete v tématu [Ironpythonu Profiler](/archive/blogs/curth/an-ironpython-profiler) (Blogy MSDN).