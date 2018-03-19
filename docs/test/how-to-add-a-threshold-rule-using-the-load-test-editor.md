---
title: "Přidání mezního pravidla pro zatížení testování v sadě Visual Studio | Microsoft Docs"
ms.date: 10/19/2016
ms.topic: article
helpviewer_keywords:
- load tests, monitoring
- load tests, thresholds
- load tests, analyzing
- thresholds in load tests
ms.assetid: 3d8fac8f-426f-4155-9ced-f7cd4c79792c
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-test
ms.openlocfilehash: b6a7551e269395fb3657aacf0c18e3212c62e53b
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/19/2018
---
# <a name="how-to-add-a-threshold-rule-using-the-load-test-editor"></a>Postupy: Přidání mezního pravidla pomocí editoru zátěžových testů

Mezní pravidla v zátěžových testech porovnávají hodnotu čítače výkonu s konstantní hodnotou nebo jinou hodnotou čítače výkonu.

## <a name="to-add-a-threshold-rule"></a>Chcete-li přidat mezní pravidlo:

1.  Otevřete zátěžový test.

2.  Rozbalte v editoru zátěžových testů **sad čítačů** uzlu.

3.  Rozbalit jednu z **kategorie čítače** v jednom ze sady čítačů. Například můžete vybrat **LoadTest:Scenario**. Rozbalte uzel.

4.  Pravým tlačítkem jeden čítače, například na **zatížení uživatele**v části **LoadTest:Scenario**. Vyberte **přidání mezního pravidla**.

     **Přidání mezního pravidla** se zobrazí dialogové okno.

5.  Lze si vybrat ze dvou typů pravidel: konstanta porovnání a čítač porovnání. Vyberte požadovaný typ a nastavte hodnoty.

    > [!NOTE]
    > Nastavte **výstrahy Pokud přes** vlastnost **True** k označení, což představuje překročení prahové hodnoty je problém, nebo **False** k označení, které spadají pod prahovou hodnotu je problém.

## <a name="see-also"></a>Viz také

- [Analýza mezních pravidel](../test/analyze-threshold-rule-violations-in-load-tests.md)
- [Určení sad čítačů a mezních pravidel pro počítače v zátěžovém testu](../test/specify-counter-sets-and-threshold-rules-for-load-testing.md)
- [Analýza výsledků zátěžových testů](../test/analyze-load-test-results-using-the-load-test-analyzer.md)
- [Určení sad čítačů a mezních pravidel pro počítače v zátěžovém testu](../test/specify-counter-sets-and-threshold-rules-for-load-testing.md)