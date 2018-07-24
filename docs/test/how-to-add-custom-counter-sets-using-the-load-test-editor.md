---
title: Přidání vlastních sad čítačů pro zátěžové testování v sadě Visual Studio
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- counters, counter sets
- counter sets
- load tests, counter sets
ms.assetid: 499aca80-1069-408d-ac68-326da6a50645
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: d9143306b9f3894e7f8f6742420f90aa30008340
ms.sourcegitcommit: 36835f1b3ec004829d6aedf01938494465587436
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/23/2018
ms.locfileid: "39204086"
---
# <a name="how-to-add-custom-counter-sets-using-the-load-test-editor"></a>Postupy: Přidání vlastních sad čítačů pomocí editoru zátěžových testů

Když vytvoříte zátěžový test pomocí **nového Průvodce zátěžovým testem**, můžete přidat počáteční sadu čítačů. Ty nabízejí sadu předdefinovaných sad čítačů pro zátěžové testy.

> [!NOTE]
> Pokud jsou zátěžové testy distribuovány napříč vzdálenými počítači, jsou čítače kontroléru a agentů namapovány na sady čítačů kontrolérů a agentů. Další informace o použití vzdálených počítačů v zátěžovém testu naleznete v tématu [testovací kontrolery a testovací agenty](configure-test-agents-and-controllers-for-load-tests.md).

Můžete spravovat čítače v **editoru zátěžových testů**. Sady čítačů, které již byly přidány do testu jsou viditelné v **sad čítačů** uzel zátěžového testu. Po vytvoření zátěžového testu k němu lze přidat nové vlastní sady čítačů.

![Vlastní sada čítačů](../test/media/loadtestcustomcounter.png)

## <a name="to-add-a-custom-counter-set-to-a-load-test"></a>Přidání vlastní sady čítačů k zátěžovému testu

1.  Otevřete zátěžový test.

2.  Rozbalte **sady čítačů** uzlu. Jsou zobrazeny všechny sady čítačů, které byly přidány do zátěžového testu.

3.  Klikněte pravým tlačítkem myši **sady čítačů** uzel a vyberte možnost **přidat vlastní sadu čítačů**.

    > [!NOTE]
    > Sadě čítačů je přidělen výchozí název, jako například **vlastní1**. Název lze změnit pomocí **vlastnosti** okna. Stisknutím klávesy **F4** zobrazíte **vlastnosti** okna.

4.  Chcete-li přidat čítače do vlastní počítadlo nastavit, klikněte pravým tlačítkem na novou sadu čítačů a klikněte na tlačítko **přidat čítače**. Další informace o přidávání čítačů naleznete v tématu [postupy: přidání čítačů do sad čítačů](../test/how-to-add-counters-to-counter-sets-using-the-load-test-editor.md).

    > [!NOTE]
    > Vlastní sadu čítačů lze také přidat kliknutím pravým tlačítkem myši na existující sadu čítačů, výběrem příkazu kopírování a následným vložením do uzlu sad čítačů. Další čítače, které jsou zkopírovány, ale nejsou vyžadovány, je možné odstranit. Můžete změnit název nové sady čítačů **vlastnosti** okna.

## <a name="see-also"></a>Viz také:

- [Určení sad čítačů a mezních pravidel pro počítače v rámci zátěžového testu](../test/specify-counter-sets-and-threshold-rules-for-load-testing.md)
- [Konfigurace parametrů spuštění zátěžového testu](../test/configure-load-test-run-settings.md)