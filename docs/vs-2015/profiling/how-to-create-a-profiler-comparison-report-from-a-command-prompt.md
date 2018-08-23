---
title: 'Postupy: vytvoření sestavy porovnání Profiler z příkazového řádku | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 00548d16-eb5b-46f7-8a65-862f98a43831
caps.latest.revision: 15
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3cb31a79af25fbe66112efd6be0aacd9b3c3820d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42668980"
---
# <a name="how-to-create-a-profiler-comparison-report-from-a-command-prompt"></a>Postupy: Vytvoření sestavy porovnání profileru z příkazového řádku
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [postupy: vytvoření sestavy porovnání Profiler z příkazového řádku](https://docs.microsoft.com/visualstudio/profiling/how-to-create-a-profiler-comparison-report-from-a-command-prompt).  
  
Můžete generovat [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] nástrojů pro profilaci sady sestav, který porovnává data o výkonu ze dvou dat profilování (. VSP nebo. Soubory VSPS). Zobrazí se sestava ukazuje rozdíly, regrese výkonu a vylepšení, ke kterým došlo v jedné relaci profilace do jiné. Hodnoty v sestavě obsahují rozdílů nebo změny, od základních hodnot v prvním souboru, který určíte. Touto položkou delta se počítá tak, že určíte rozdíl mezi původní hodnotu, která je základní hodnota a hodnota výsledku z nové analýzy. Porovnání dat profiler může být založen na funkce v kódu, moduly v aplikaci, řádky, ukazatele na instrukce (IP) a typy.  
  
 Pro výčet identifikátorů porovnání kategorií a pole, zadejte na příkazovém řádku následující:  
  
 **VSPerfReport/querydifftables***VspFileName1* *VspFileName2*   
  
 Použijte následující syntaxi pro vytvoření sestavy porovnání:  
  
 **VSPerfReport/diff** `VspFileName1` *VspFileName2* [**/**`Options`]    
  
 Z následující tabulky můžete přidat možnosti **VSPerfReport/diff** příkazového řádku.  
  
|Možnost|Popis|  
|------------|-----------------|  
|**DiffThreshold:**[*hodnotu*]|Rozdíl ignorujte, pokud byl pod tuto procentuální prahovou hodnotu. Také se nezobrazí nová data s hodnotami, které jsou pod touto prahovou hodnotou.|  
|**DiffTable:** *TableName*|Pomocí této tabulce můžete porovnat soubory. Ve výchozím nastavení se používá tabulka funkcí. Zadejte identifikátor, který je uveden v **VSPerfReport/querydifftables**.|  
|**DiffColumn:** *Názevsloupce*|Tento sloupec slouží k porovnání hodnoty. Ve výchozím nastavení se používá sloupec procent výhradních vzorků. Zadejte identifikátor, který je uveden v **VSPerfReport/querydifftables**.|



