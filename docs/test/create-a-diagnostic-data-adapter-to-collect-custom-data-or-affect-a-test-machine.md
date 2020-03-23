---
title: Vytvoření adaptéru diagnostických dat pro testování
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- Diagnostic Data Adapter [Visual Studio ALM]
- Diagnostic Data Adapter
ms.assetid: b0b53fae-7007-4ad9-a604-21685937622f
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 91e5f9b3cee9cdfc2ca85c39c701b87028ad949a
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2020
ms.locfileid: "75585203"
---
# <a name="create-a-diagnostic-data-adapter-to-collect-custom-data-or-affect-a-test-machine"></a>Vytvoření adaptéru diagnostických dat pro shromažďování vlastních dat nebo ovlivnění testovacího počítače

Může být vhodné vytvořit vlastní adaptér diagnostiky dat ke sběru dat při spuštění testu nebo v průběhu testu ovlivnit testovací počítač. Může být například užitečné shromáždit soubory protokolu, které jsou vytvářeny v testované aplikaci, a připojit je k výsledkům testu, nebo spustit testy, když máte málo zbývajícího místa na disku. Pomocí api k dispozici v sadě Visual Studio Enterprise, můžete napsat kód k provádění úkolů v určitých bodech v testovacím běhu. Lze například provádět úkoly při spuštění testovacího běhu, před spuštěním nebo po spuštění jednotlivých testů, a když se testovací běh dokončí.

Lze zadat výchozí vstup do vlastního adaptéru diagnostiky dat pomocí souboru konfiguračních nastavení. Lze například zadat informace o umístění souboru, který chcete shromáždit a připojit k výsledkům testu, nebo o tom, kolik by mělo na disku v systému zůstat místa. Tato data lze nakonfigurovat pro každé nastavení testu, které vytvoříte. Může být zobrazen a editován pomocí výchozího editoru dodávaného s Microsoft Test Manager nebo můžete vytvořit vlastní uživatelský ovládací prvek pro použití jako editor. Jakékoli změny provedené v konfiguraci adaptéru v editoru jsou uloženy s nastavením testu.

Pokud spouštěte testy z aplikace Visual Studio, musíte nastavit tato nastavení testu tak, aby byla aktivní. Další informace o nastavení testu naleznete v [tématu Shromažďování diagnostických informací pomocí nastavení testu](../test/collect-diagnostic-information-using-test-settings.md).

[!INCLUDE [web-load-test-deprecated](includes/web-load-test-deprecated.md)]

## <a name="tasks"></a>Úlohy

Následující témata vám pomohou s vytvořením Adaptérů diagnostiky dat:

|Úlohy|Související témata|
|-|-----------------------|
|**Vytvoření adaptéru diagnostických dat:** Adaptér diagnostických dat vytvoříte vytvořením knihovny tříd a potom pomocí rozhraní API adaptéru diagnostických dat shromážděte požadované informace nebo ovlivněte testovací systém, který používáte ke spuštění testů.|-   [Postup: Vytvoření adaptéru diagnostických dat](../test/how-to-create-a-diagnostic-data-adapter.md)|
|**Výběr vlastního adaptéru diagnostických dat, který se má použít při spuštění testů:** Můžete vybrat, který adaptér diagnostických dat se má použít pro nastavení testu, aby se adaptér použil při spuštění testů.|-   [Shromažďování diagnostických dat během testování (plány testů Azure)](/azure/devops/test/collect-diagnostic-data?view=vsts)<br />-   [Shromažďování diagnostických dat v ručních testech (plány testů Azure)](/azure/devops/test/mtm/collect-more-diagnostic-data-in-manual-tests?view=vsts)|

## <a name="see-also"></a>Viz také

- [Shromažďování diagnostických informací pomocí nastavení testu](../test/collect-diagnostic-information-using-test-settings.md)
