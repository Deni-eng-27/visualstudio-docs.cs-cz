---
title: 'Postupy: Určení vzorkovací frekvence pro spuštění zátěžového testu'
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, run settings
ms.assetid: 51cbe7d6-5dfd-4842-bca3-f7f8a665dc84
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: c1e94bb6da2786b989208ea1104d509883bc0724
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60042194"
---
# <a name="how-to-specify-the-sample-rate-for-a-load-test-run-setting"></a>Postupy: Určení vzorkovací frekvence pro spuštění zátěžového testu

Po vytvoření zátěžového testu pomocí **nového Průvodce zátěžovým testem**, můžete použít **editoru zátěžového testu** Chcete-li změnit vlastnosti tak, aby vyhovovaly potřebám a cílům testování.

[!INCLUDE [web-load-test-deprecated](includes/web-load-test-deprecated.md)]

Použití **editoru zátěžových testů**, můžete upravit nastavení spuštění **vzorkovací frekvence** hodnotu vlastnosti v **vlastnosti** okna. Úplný seznam vlastností parametrů spuštění a jejich popis najdete v části [zátěžového testu spusťte nastavení](../test/load-test-run-settings-properties.md).

Zvolte příslušnou hodnotu **vzorkovací frekvence** vlastnost pro spuštění zátěžového testu na základě délky zátěžového testu. Menší vzorkovací frekvence, jako je například výchozí hodnota pěti sekund, vyžaduje více místa v databázi výsledků zátěžového testu. Pro delší zátěžové testy vzorkovací frekvence snižuje množství dat, která shromažďujete. Další informace najdete v tématu [jak: Určení vzorkovací frekvence pro spuštění zátěžového testu](../test/how-to-specify-the-sample-rate-for-a-load-test.md).

Zde jsou uvedeny pokyny pro vzorkovací frekvence:

|Doba trvání zátěžového testu|Doporučená frekvence vzorkování|
|-|-----------------------------|
|\< 1 hodina|5 sekund|
|1 - 8 hodin|15 sekund|
|8 - 24 hodin|30 sekund|
|> 24 hodin|60 sekund|

## <a name="to-specify-performance-counter-sampling-rate-in-a-run-setting"></a>Chcete-li určit míry vzorkování čítače výkonu v nastavení spuštění

1. Otevřete zátěžový test.

     **Editoru zátěžových testů** se zobrazí. Zobrazí se strom zátěžového testu.

2. V zátěžového testování stromu v **parametrů běhu** složky, zvolte, kterou chcete určení vzorkovací frekvence pro parametr spuštění.

3. Na **zobrazení** nabídce vyberte možnost **okno vlastností**.

     Spuštění načtení nastavení uživatele kategorie a vlastnosti jsou zobrazeny v **vlastnosti** okna.

4. V **vzorkovací frekvence** vlastnost, zadejte hodnotu času, která určuje četnost, kdy bude zátěžový test shromažďovat data čítačů výkonu.

5. Po dokončení změn vlastnosti, zvolte **Uložit** na **souboru** nabídky. Potom můžete spustit zátěžový test pomocí nového **vzorkovací frekvence** hodnotu.

## <a name="see-also"></a>Viz také:

- [Konfigurace parametrů spuštění zátěžového testu](../test/configure-load-test-run-settings.md)
- [Vlastnosti scénáře zátěžového testu](../test/load-test-scenario-properties.md)