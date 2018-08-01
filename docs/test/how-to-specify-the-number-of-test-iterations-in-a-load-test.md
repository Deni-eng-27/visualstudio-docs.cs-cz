---
title: Určení počtu testovacích iterací v běhu zátěžového testu v sadě Visual Studio
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, properties
- load tests, run settings
ms.assetid: 45a625db-b3e7-4d64-beda-b9a76248096d
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: a94a5681c0348e6e08f9d777ecebaa3e69886cfe
ms.sourcegitcommit: 495bba1d8029646653f99ad20df2f80faad8d58b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/31/2018
ms.locfileid: "39379492"
---
# <a name="how-to-specify-the-number-of-test-iterations-in-a-load-test-run-setting"></a>Postupy: určení počtu testovacích iterací v nastavení spuštění zátěžového testu

Po vytvoření zátěžového testu pomocí **nového Průvodce zátěžovým testem**, můžete použít **editoru zátěžového testu** Chcete-li změnit vlastnosti scénářů pro splnění potřebám a cílům testování. Další informace najdete v tématu [návod: vytvoření a spuštění zátěžového testu](../test/walkthrough-create-and-run-a-load-test.md).

Použití **editoru zátěžových testů**, můžete upravit **testovacích iterací** vlastností hodnoty parametrů spuštění v **vlastnosti** okna. **Testovací iterace** vlastnost určuje počet iterací pro spuštění na všechny webové testy výkonu a jednotky ve všech scénářích v testu zatížení pomocí **editoru zátěžového testu**.

> [!NOTE]
> Úplný seznam vlastností parametrů spuštění a jejich popis najdete v části [zátěžového testu spusťte nastavení](../test/load-test-run-settings-properties.md).


## <a name="to-specify-the-number-of-test-iterations-in-a-run-setting"></a>K určení počtu testovacích iterací v nastavení spuštění

1.  Otevřete zátěžový test.

     **Editoru zátěžového testu** zobrazí se strom zátěžového testu.

2.  V zátěžového testování v stromu **parametrů běhu** složky, zvolte nastavení spuštění.

3.  Na **zobrazení** nabídce vyberte možnost **okno vlastností** zobrazíte zatížení systémy kategorie nastavení a vlastnosti.

4.  Nastavte **iterace testu použijte** vlastnost **True**.

5.  V **testovací iterace** vlastnost, zadejte číslo určující počet iterací testu ke spuštění během zátěžového testu.

6.  Po dokončení změn vlastnosti, zvolte **Uložit** na **souboru** nabídky. Potom můžete spustit zátěžový test pomocí nového **testovací iterace** hodnotu.

## <a name="see-also"></a>Viz také:

- [Konfigurace parametrů spuštění zátěžového testu](../test/configure-load-test-run-settings.md)
- [Vlastnosti scénáře zátěžového testu](../test/load-test-scenario-properties.md)