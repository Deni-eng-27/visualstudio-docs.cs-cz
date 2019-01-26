---
title: Uložit protokol testu zatížení pro neúspěšné testy
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, scenarios
- load tests, logging
ms.assetid: 08a7fe98-a7f7-4b8d-94a3-ec82b65a2aaf
author: gewarren
ms.author: gewarren
manager: jillfra
ms.prod: visual-studio-dev15
ms.openlocfilehash: f35d4488add1f66ef8ee57d3a2b1125c4284ef9b
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54932555"
---
# <a name="how-to-specify-if-test-failures-are-saved-to-test-logs-using-the-load-test-editor"></a>Postupy: Určení, zda jsou ukládána selhání testů pro testování protokolů pomocí editoru zátěžových testů

Po vytvoření zátěžového testu pomocí **nového Průvodce zátěžovým testem**, můžete použít **editoru zátěžového testu** Chcete-li změnit vlastnosti zátěžového testu odpovídá potřebám a cílům testování. Zobrazit [názorný postup: Vytvoření a spuštění zátěžového testu](../test/walkthrough-create-and-run-a-load-test.md). Můžete zadat, pokud chcete protokol testu uložit Pokud selhání testu v rámci zátěžového testu tak, že změníte **při selhání testu uložit protokol** vlastnost.

> [!NOTE]
> Úplný seznam vlastností parametrů spuštění a jejich popis najdete v části [zátěžového testu spusťte nastavení](../test/load-test-run-settings-properties.md).

[!INCLUDE [web-load-test-deprecated](includes/web-load-test-deprecated.md)]

## <a name="to-specify-if-the-test-log-is-saved-when-a-test-fails-in-a-scenario"></a>Určení, zda bude protokol testu při selhání testu ve scénáři uložen

1.  Otevřete zátěžový test.

     **Editoru zátěžových testů** se zobrazí. Zobrazí se strom zátěžového testu.

2.  V zátěžového testu stromů **parametrů běhu** složky, vyberte uzel parametrů spuštění, který chcete zadat maximální počet iterací testu.

3.  Na **zobrazení** nabídce vyberte možnost **okno vlastností**.

     Vlastnosti parametrů běhu kategorií a jsou zobrazeny v **vlastnosti** okna.

4.  V **při selhání testu uložit protokol** vlastnosti, vyberte buď **True** nebo **False** k určení, zda chcete uložit protokol testu v případě selhání testu ve scénáři.

     Po dokončení změn vlastnosti, zvolte **Uložit** na **souboru** nabídky.

     Data uložená v protokolu lze zobrazit pomocí tabulkového zobrazení v Analyzéru zátěžového testu. Další informace najdete v tématu [Analýza výsledků zátěžových testů a chyb v tabulkovém zobrazení](../test/analyze-load-test-results-and-errors-in-the-tables-view.md).

## <a name="see-also"></a>Viz také:

- [Úpravy scénářů zátěžových testů](../test/edit-load-test-scenarios.md)
- [Návod: Vytvoření a spuštění zátěžového testu](../test/walkthrough-create-and-run-a-load-test.md)