---
title: Nastavení protokolování zátěžových testů
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, logging, modifying
ms.assetid: 9649226a-857d-41ef-8ec7-047b6e498033
author: gewarren
ms.author: gewarren
manager: jillfra
ms.prod: visual-studio-dev15
ms.openlocfilehash: e00f31dac1cf6b5ac329e51040027e94d4813dcb
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55036404"
---
# <a name="modify-load-test-logging-settings"></a>Úprava nastavení protokolování zátěžového testu

Výsledek dokončeného zátěžového testu obsahuje vzorky čítače výkonu a informace o chybách pravidelně shromažďované z testovaných počítačů do protokolu. V průběhu spuštění zátěžového testu lze shromažďovat velké množství vzorků čítačů výkonu. Množství shromážděných dat o výkonu závisí na délce běhu, intervalu vzorkování, počtu testovaných počítačů a počtu shromažďovaných čítačů. U velkých zátěžových testů může množství shromážděných dat o výkonu snadno dosáhnout několika GB, proto zvažte úpravu četnosti ukládání dat do protokolu. Zobrazit [testovací kontrolery a testovací agenty](configure-test-agents-and-controllers-for-load-tests.md).

[!INCLUDE [web-load-test-deprecated](includes/web-load-test-deprecated.md)]

*Testovací kontrolér* zařadí za všechny vzorkovací data shromážděná zátěžového testu do protokolu databáze, když je spuštěn test. Další data, jako jsou podrobnosti časování a podrobnosti o chybě, se načtou do databáze po dokončení testu.

|Úloha|Související témata|
|-|-----------------------|
|**Uložení protokolů, pokud zátěžový test selže:** Můžete určit, jestli chcete při každém selhání testu uložit protokol testu.|-   [Jak: Určení, zda jsou selhání testu ukládána do protokolů testování](../test/how-to-specify-if-test-failures-are-saved-to-test-logs.md)|
|**Nastavte maximální velikost souboru protokolu:** Můžete upravit konfigurační soubor XML, který je přidružený k službě kontroleru testů zadat maximální velikost souboru, který chcete použít pro soubor protokolu.|[Postupy: Zadejte maximální velikost souboru protokolu](../test/how-to-specify-the-maximum-size-for-the-log-file.md)|

## <a name="see-also"></a>Viz také:

- [Konfigurace parametrů spuštění zátěžového testu](../test/configure-load-test-run-settings.md)