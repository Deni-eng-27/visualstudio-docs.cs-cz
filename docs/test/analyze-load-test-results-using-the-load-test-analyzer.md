---
title: Analýza výsledků zátěžových testů
ms.date: 10/20/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, test results
- load tests, analyzing test results
- load tests, managing test results
ms.assetid: 8a4ba300-425d-447c-91d9-c53f4345feee
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: d3cd641a6361a8cf555e722ccd6c42414f5bdbe7
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68926435"
---
# <a name="analyze-load-test-results-using-the-load-test-analyzer"></a>Analýza výsledků zátěžových testů pomocí Analyzéru zátěžového testu

Nalezení problémových míst, identifikovat chyby a měřit zlepšení ve vaší aplikaci, když použijete **Analyzéru zátěžového testu**.

[!INCLUDE [web-load-test-deprecated](includes/web-load-test-deprecated.md)]

Analýza výsledků zátěžových testů v těchto způsobů:

- Sledujte zátěžový test, když je spuštěn.

- Analyzujte test zatížení po jeho dokončení.

- Zobrazení výsledků z předchozího testu zatížení.

Můžete také vytvořit sestavy, které porovnávají dva nebo více sestav pro analýzu trendů sdílet se zúčastněnými stranami. Zobrazit [sestav zátěžové testy s výsledky pro porovnávání testů a analýzu trendů](../test/compare-load-test-results.md).

Tyto kroky můžete udělat, jestli spuštění zátěžového testu ze sady Visual Studio Enterprise nebo z příkazového řádku a určuje, zda spustit zátěžový test v jednom počítači nebo ve vzdáleném počítači.

## <a name="differences-between-analyzing-a-running-and-a-completed-load-test"></a>Rozdíly mezi analýzy spuštěné a dokončeného zátěžového testu

Při spuštění zátěžového testu **Analyzéru zátěžového testu** zobrazí na samostatné kartě, společně s názvem vašeho testu zatížení a čas, který byl spuštěn test (třeba **LoadTest1 [12:40 hodin]** ). Při běhu zátěžového testu, menší sady dat čítače výkonu se zachová v paměti. Tato sada dat můžete sledovat, při spuštění zátěžového testu. Po dokončení zátěžového testu můžete analyzovat kompletní data z databáze. Existují rozdíly v jaká data se zobrazí, když běží zátěžové testy a co data, která se zobrazí po zátěžového testu byla dokončena. Například 90 až 95 procent data o době odezvy se nevypočítá až do dokončení zátěžového testu. Několik rozdílů dojít také funkčnosti nástroje, které jsou k dispozici, pokud chcete analyzovat data.

Při spuštění zátěžového testu jsou k dispozici dvě zobrazení: Zobrazení **grafů** a zobrazení **tabulek** . **Grafy** zobrazení vám umožní graf čítače výkonu, které se shromažďují. **Tabulky** zobrazení poskytuje informace o jednotlivých testů, stránek, transakce a požadavky, které byly shromážděny. Získáte také tabulku, která se zobrazí seznam chyb.

Ve výchozím nastavení po dokončení zátěžového testu **Souhrn** zobrazení. Můžete přepínat mezi **Souhrn**, **grafy**, **tabulky**, a **podrobnosti** zobrazeními pomocí panelu nástrojů. **Analyzéru zátěžového testu** můžete ukotvit nebo nastavit jako plovoucí prvek pomocí obvyklých technik zpracování okno Visual Studio. Při analýze spuštění dokončeného zátěžového testu můžete mít více **zatížení testování analyzátory** otevřít ve stejnou dobu pro porovnání různých zátěžový test běží.

## <a name="tasks"></a>Úlohy

|Úlohy|Související témata|
|-|-|
|**Přístup k výsledkům zátěžového testu:** Když spustíte zátěžový test z editoru zátěžových testů, výsledky zátěžového testu se automaticky otevře a spuštění zátěžového testu se zobrazí v **Analyzéru zátěžového testu**.|-   [Jak: Přístup k výsledkům zátěžového testu pro analýzu](../test/how-to-access-load-test-results-for-analysis.md)|
|**Přidejte poznámky k analýze pro zátěžový test:** Můžete přidat komentáře k zátěžovým testům při provádění analýz. Komentáře jsou uloženy trvale, společně s výsledkem zátěžového testu. Popis, který můžete zadat také zobrazí v **popis** sloupec, který je spojen se zátěžovým testem v **otevřít a spravovat výsledky testu** dialogové okno v editoru zátěžového testu.<br /><br /> Další informace najdete v tématu [jak: Přístup k výsledkům zátěžového](../test/how-to-access-load-test-results-for-analysis.md)testu pro analýzu.<br /><br /> Kromě toho komentáře se zobrazí, když vytváříte sestavu aplikace Excel pro zatížení výsledky testů.<br /><br /> Další informace najdete v tématu [sestav zátěžové testy s výsledky pro porovnávání testů a analýzu trendů](../test/compare-load-test-results.md).||
|**Analýza výsledků zátěžového testu:** Po přístupu k datům spuštění zátěžového testu můžete analyzovat výsledná data. Můžete zobrazit souhrn zátěžového testu rychle porozumět výsledky. Souhrn zátěžového testu zobrazí klíčové výsledky ve formátu kompaktní a snadno čtení.<br /><br /> Souhrn zátěžového testu můžete vytisknout. Je to vhodné pro použití při komunikaci výsledky účastníkům.<br /><br /> Podrobnosti o výsledky zátěžového testu můžete analyzovat pomocí grafů a tabulek ve výsledcích. Patří mezi ně **chyby**, **stránky**, **požadavky**, **trasování SQL**, **testy**,  **Prahové hodnoty**, a **transakce**.|-   [Přehled souhrnu výsledků zátěžového testu](../test/load-test-results-summary-overview.md)<br />-   [Jak: Zobrazit odpověď webové stránky](../test/how-to-view-web-page-response-time-in-a-load-test.md)<br />-   [Analýza mezních pravidel](../test/analyze-threshold-rule-violations-in-load-tests.md)<br />-   [Analýza výsledků zátěžových testů v zobrazení grafů](../test/analyze-load-test-results-in-the-graphs-view.md)<br />-   [Analýza výsledků zátěžových testů a chyb v tabulkovém zobrazení](../test/analyze-load-test-results-and-errors-in-the-tables-view.md)|
|**Analýza aktivity virtuálních uživatelů ve výsledcích zátěžového testu pro izolaci potíží s výkonem:** Graf aktivity virtuálního uživatele můžete použít k vizualizaci toho, co virtuální uživatelé provádějí během zátěžového testu. To může pomoci izolovat poraďte se špičkami Procesorem nebo výpadky požadavků za sekundu a určit, které testy nebo stránky jsou spuštěny během těchto provozní špičky a drops.|-   [Analýza aktivity virtuálních uživatelů v podrobném zobrazení](../test/analyze-load-test-virtual-user-activity-in-the-details-view.md)|