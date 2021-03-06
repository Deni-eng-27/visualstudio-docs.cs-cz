---
title: Nastavení parametrů běhu zátěžového testu z příkazového řádku
ms.date: 10/19/2016
ms.topic: how-to
helpviewer_keywords:
- load tests, command line
- load tests, run settings, selecting
ms.assetid: 175d1d58-f09a-4449-b132-a29a394a7c8e
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 79f1cc833278a62e2871cdc725f5993b12bcdb60
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "85287555"
---
# <a name="how-to-select-a-load-test-run-setting-to-use-from-the-command-line"></a>Postupy: výběr nastavení běhu zátěžového testu pro použití z příkazového řádku

Zátěžový test může zahrnovat *parametry spuštění*, které jsou vlastnosti, které ovlivňují způsob spuštění zátěžového testu. Nastavení spuštění jsou uspořádána podle kategorií v okně **vlastnosti** . Zátěžový test při svém spuštění používá parametry spuštění, které jsou aktuálně nastaveny jako aktivní.

Pokud zátěžový test obsahuje pouze jeden parametr spuštění, jedná se vždy o aktivní uzel. Pokud zátěžový test obsahuje více uzlů parametrů spuštění, můžete vybrat, který má být použit při spuštění zátěžového testu z příkazového řádku. Viz [Postupy: Přidání dalších parametrů spuštění do zátěžového testu](../test/how-to-add-additional-run-settings-to-a-load-test.md).

[!INCLUDE [web-load-test-deprecated](includes/web-load-test-deprecated.md)]

## <a name="to-change-the-run-setting-from-the-command-line"></a>Změna nastavení spuštění z příkazového řádku

1. Pokud chcete použít jiné parametry spuštění z příkazového řádku a využít přitom strategii kontextového parametru, použijte následující příkaz:

    `Set Test.UseRunSetting= CorporateStagingWebServer`

2. Spusťte zátěžový test pomocí nástroje mstest:

    `mstest /testcontainer:loadtest1.loadtest`

## <a name="see-also"></a>Viz také

- [Konfigurovat nastavení běhu zátěžového testu](../test/configure-load-test-run-settings.md)
- [Určení sad čítačů a mezních pravidel pro počítače v zátěžovém testu](../test/specify-counter-sets-and-threshold-rules-for-load-testing.md)
- [Postupy: Přidání dalších parametrů spuštění do zátěžového testu](../test/how-to-add-additional-run-settings-to-a-load-test.md)
- [Postupy: výběr aktivního nastavení spuštění pro zátěžový test](../test/how-to-select-the-active-run-setting-for-a-load-test.md)
