---
title: "Přidání značek počítače do mapování nastavit čítače pro zatížení testování v sadě Visual Studio | Microsoft Docs"
ms.date: 10/19/2016
ms.topic: article
helpviewer_keywords:
- load tests, counter set mappings, computer tags
ms.assetid: f52a73e1-036a-4b28-a6c8-848284bf4488
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-test
ms.openlocfilehash: 70f3f2c58974478b17c78c3de4014a1921accd76
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/19/2018
---
# <a name="how-to-add-computer-tags-to-counter-set-mappings-using-the-load-test-editor"></a>Postupy: Přidání značek počítače do mapování sad čítačů pomocí editoru zátěžových testů

Značky počítače umožňují identifikovat počítač s názvem snadno rozpoznat. Zadané značky jsou zobrazeny v **čítač nastavit mapování** uzel ve stromu v editoru zátěžových testů. Důležitější, značky se zobrazí v sestavách aplikace Excel, které pomáhá identifikovat zúčastněným stranám jakou roli má počítač v zátěžovém testu. Například "Web Server1 v lab2" nebo "Server2 SQL v Phoenix office". Další informace najdete v tématu [Reporting výsledků zátěžových testů pro porovnávání testů a analýzu trendů](../test/compare-load-test-results.md).

## <a name="to-add-a-tag-to-a-computer"></a>Chcete-li přidat značky do počítače

1.  Otevřete zátěžový test.

2.  Vyberte **Správa sad čítačů** tlačítko.

     – nebo –

     Klikněte pravým tlačítkem na **sad čítačů** složky v zatížení testování stromu a zvolte **Správa sad čítačů**.

     **Správa sad čítačů** se zobrazí dialogové okno.

3.  (Volitelné) V **vybrané počítače a sad čítačů bude přidán pod následující parametry spuštění** vyberte jiné nastavení spuštění.

    > [!NOTE]
    > To platí jenom Pokud máte více než jedno spuštění nastavení v zátěžovém testu.

4.  V části **počítače a čítač nastaví monitorování**, vyberte počítač, který chcete použít na značku a tím.

    > [!NOTE]
    > Informace o tom, jak přidat počítač, který najdete v tématu [postupy: Správa sad čítačů](../test/how-to-manage-counter-sets-using-the-load-test-editor.md).

5.  V **značek počítače** textového pole, zadejte značky pro přidružení k počítači. Například "TestMachine12 v lab3".

6.  Zvolte **OK**.

## <a name="see-also"></a>Viz také

- [Analýza mezních pravidel](../test/analyze-threshold-rule-violations-in-load-tests.md)
- [Analýza výsledků zátěžových testů](../test/analyze-load-test-results-using-the-load-test-analyzer.md)
- [Určení sad čítačů a mezních pravidel pro počítače v zátěžovém testu](../test/specify-counter-sets-and-threshold-rules-for-load-testing.md)
- [Postupy: Správa sad čítačů](../test/how-to-manage-counter-sets-using-the-load-test-editor.md)