---
title: Zobrazení interakce vrstvy | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.view.tierinteraction
helpviewer_keywords:
- Tier Interactions view
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4636a391e2472dbff427956077719e75f34a81de
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
ms.locfileid: "31584968"
---
# <a name="tier-interactions-view"></a>Zobrazení interakcí vrstev

Profilace interakce vrstvy poskytuje další informace o dobu provádění funkcí možných aplikací, které komunikují s databází prostřednictvím [!INCLUDE[vstecado](../data-tools/includes/vstecado_md.md)]. Data jsou shromažďována jenom pro funkce synchronní volání.

**Požadavky**

- Visual Studio Enterprise

Zobrazení interakcí zobrazí dat interakce vrstev v dvě podokna:

- V hlavním podokně je hierarchickou stromovou strukturu. Řádek nejvyšší úrovně obsahuje agregovaná data pro připojení databáze [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] stránky nebo proces. Podřízené uzly obsahovat agregovaná data pro připojení databáze nadřazeného objektu.

- Při kliknutí na uzel volání databáze v hlavním podokně, v podokně podrobností se zobrazí data pro instanci databáze volání.

 Čas se zobrazí jako počet milisekund, po nebo počet taktů procesoru. Změnit časovou jednotku zobrazí, klikněte na **nástroje** nabídky, klikněte na tlačítko **možnosti**a pak vyberte jednu z **zobrazit čas hodnoty jako** možnosti.

## <a name="master-pane"></a>Hlavní podokno

|Sloupec|Popis|
|------------|-----------------|
|**Jméno**|-Pro řádek nejvyšší úrovně, název PROFILOVANÉHO procesu nebo webové stránky.<br />-Pro řádek připojení databáze, název serveru, který je hostitelem databáze.|
|**Databáze**|Název databáze (pouze řádky připojení databáze).|
|**Počet**|Celkový počet požadavků, které jsou generovány podle procesu, webovou stránku nebo připojení k databázi.|
|**Celkem uběhlý čas**|Celková doba, která je potřebná k provedení jakékoli jeden požadavek z procesu, webovou stránku nebo připojení k databázi.|
|**Maximální uplynulý čas**|Maximální doba potřebná k provedení jakékoli jeden požadavek z procesu, webovou stránku nebo připojení k databázi.|
|**Uplynulý čas operace min.**|Minimální doba, která je potřebná k provedení jakékoli jeden požadavek z procesu, webovou stránku nebo připojení k databázi.|
|**Prům. uplynulý čas**|Průměrná doba, která je potřebná k provedení požadavku z procesu, webovou stránku nebo připojení k databázi.|

## <a name="database-connection-details-pane"></a>Podokno Podrobnosti připojení databáze

|Sloupec|Popis|
|------------|-----------------|
|**Text příkazu**|Příkaz jazyka SQL požadavku.|
|**Počet dotazů**|Počet spuštění dotazu.|
|**Celkem uběhlý čas**|Celková doba, která je potřebná k provedení instance dotazu.|
|**Maximální uplynulý čas**|Maximální doba, která je potřebná k provedení jakékoli jednu instanci dotazu.|
|**Uplynulý čas operace min.**|Minimální čas, který je potřebná k provedení jakékoli jednu instanci dotazu.|
|**Prům. uplynulý čas**|Průměrná doba, která je potřebná k provedení instance dotazu.|