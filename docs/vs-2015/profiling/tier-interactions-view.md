---
title: Zobrazení interakcí vrstev | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.view.tierinteraction
helpviewer_keywords:
- Tier Interactions view
ms.assetid: bb4fb21c-f3f7-473a-8b5e-442da4c2c445
caps.latest.revision: 20
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: bd60c855bacaf62beec47c9f977d0ab220ce7ca6
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "68145526"
---
# <a name="tier-interactions-view"></a>Zobrazení interakcí vrstev
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Profilace interakce vrstev poskytuje další informace o časech spuštění ve funkcích vícevrstvých aplikací, které komunikují s databázemi prostřednictvím [!INCLUDE[vstecado](../includes/vstecado-md.md)] . Data jsou shromažďována pouze pro volání synchronních funkcí.  
  
 **Požadavky**  
  
- [!INCLUDE[vsUltLong](../includes/vsultlong-md.md)]  
  
  Zobrazení interakcí zobrazuje data interakce vrstev ve dvou podoknech:  
  
- Podokno předlohy je hierarchický strom. Řádek nejvyšší úrovně obsahuje agregovaná data pro databázová připojení [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] stránky nebo procesu. Podřízené uzly obsahují agregovaná data pro databázová připojení nadřazeného objektu.  
  
- Po kliknutí na uzel volání databáze v podokně předloha se v podokně podrobností zobrazí data instance volání databáze.  
  
  Čas se zobrazuje jako počet milisekund nebo počet taktů procesoru. Chcete-li změnit zobrazenou časovou jednotku, klikněte na nabídku **nástroje** , klikněte na položku **Možnosti**a potom zvolte jednu z **hodnot zobrazit čas jako** možnosti.  
  
## <a name="master-pane"></a>Podokno předlohy  
  
|Sloupec|Popis|  
|------------|-----------------|  
|**Name**|– Pro řádek nejvyšší úrovně, název profilované procesu nebo webové stránky.<br />– Pro řádek připojení databáze název serveru, který je hostitelem databáze.|  
|**Databáze**|Název databáze (pouze řádky připojení databáze).|  
|**Výpočtu**|Celkový počet požadavků, které jsou generovány procesem, webovou stránkou nebo připojením k databázi.|  
|**Celkový uplynulý čas**|Celkový čas strávený prováděním jedné žádosti z procesu, webové stránky nebo připojení k databázi.|  
|**Maximální uplynulý čas**|Maximální doba strávená prováděním jedné žádosti z procesu, webové stránky nebo připojení k databázi.|  
|**Minimální uplynulý čas**|Minimální čas strávený prováděním jedné žádosti z procesu, webové stránky nebo připojení k databázi.|  
|**Průměrný uplynulý čas**|Průměrná doba, kterou strávily vykonání požadavku z procesu, webové stránky nebo připojení k databázi.|  
  
## <a name="database-connection-details-pane"></a>Podokno podrobností připojení databáze  
  
|Sloupec|Popis|  
|------------|-----------------|  
|**Text příkazu**|Dotaz SQL žádosti|  
|**Počet dotazů**|Počet, kolikrát se dotaz spustil.|  
|**Celkový uplynulý čas**|Celkový čas strávený prováděním instancí dotazu.|  
|**Maximální uplynulý čas**|Maximální čas strávený prováděním libovolné instance dotazu.|  
|**Minimální uplynulý čas**|Minimální čas strávený prováděním jedné instance dotazu.|  
|**Průměrný uplynulý čas**|Průměrná doba strávená prováděním instance dotazu.|
