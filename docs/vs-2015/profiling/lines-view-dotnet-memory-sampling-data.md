---
title: Zobrazení řádků – Data vzorkování paměti .NET | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Lines view
ms.assetid: 6631ab87-0e62-4c76-a063-4ea7222b07da
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a3aa0c91cb6f26dd2a914195791c12421798c43b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42633634"
---
# <a name="lines-view---net-memory-sampling-data"></a>Zobrazení řádků – data vzorkování paměti .NET
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [zobrazení řádků – Data vzorkování paměti .NET](https://docs.microsoft.com/visualstudio/profiling/lines-view-dotnet-memory-sampling-data).  
  
Zobrazení řádků pro .NET profilování data o přidělování paměti, která používá metody vzorkování seznam příkazů, které přidělené paměti během spuštění profilování. Sloupce, které zahrnují také velikost a počet přidělení.  
  
 Ve zdrojovém souboru příkaz se týkají více než jeden řádek ve zdrojovém souboru a jeden řádek může obsahovat více než jeden výraz.  
  
 Příkaz je identifikován následující:  
  
-   Zdrojový soubor, který obsahuje Function – příkaz  
  
-   Funkce, která obsahuje příkaz.  
  
-   Zdrojový řádek, ve kterém se spustí příkaz.  
  
-   Znak ve zdrojovém řádku, ve kterém se spustí příkaz.  
  
-   Řádku zdroje, u které končí příkaz.  
  
-   Znak ve zdrojovém řádku, kdy příkaz skončí.  
  
 Sloupec název řádek obsahuje seřaditelné zřetězení těchto dat identifikátor.  
  
 Podle definice příkazu nevolá dalších funkcí. Proto jsou uvedeny pouze výhradní hodnoty.  
  
|Sloupec|Popis|  
|------------|-----------------|  
|**ID procesu**|ID procesu (PID) běhu profilování.|  
|**Název procesu**|Název procesu.|  
|**Název modulu**|Název modulu, který obsahuje příkaz.|  
|**Cesta modulu**|Cesta k napadenému modulu, který obsahuje příkaz.|  
|**Zdrojový soubor**|Zdrojový soubor, který obsahuje příkaz.|  
|**Název funkce**|Název funkce, která obsahuje příkaz.|  
|**Číslo řádku funkce**|Číslo řádku začátku této funkce ve zdrojovém souboru.|  
|**Adresa funkce**|Počáteční adresa funkce.|  
|**Začátek řádku zdroje**|Počáteční řádek číslo ve zdrojovém souboru, ve kterém došlo k chybě přidělení paměti.|  
|**Konec řádku zdroje**|Koncové číslo řádku ve zdrojovém souboru, ve kterém došlo k chybě přidělení paměti.|  
|**Počáteční znak zdrojového kódu**|Odsazení počátečního znaku ve zdrojovém souboru řádku, ve kterém došlo k chybě přidělení paměti.|  
|**Koncový znak zdrojového kódu**|Posun koncového znaku ve zdrojovém souboru řádku, ve kterém došlo k chybě přidělení paměti.|  
|**Název čáry**|Identifikátor generovaný profileru řádku pomocí následující syntaxe:`Source File`**; [** `Line Number Start` **,**`Character Start`**] ->; [**`Line Number Start,Character Start`**]**|  
|**Výhradní přidělení**|Celkový počet objektů, které byly vytvořeny v tomto řádku.|  
|**% Výhradních přidělení**|Procento všech objektů, které byly vytvořeny při spuštění profilace, které byly přiděleny v tomto řádku.|  
|**Výhradní bajty**|Procento všech počet bajtů paměti, které byly přiděleny při spuštění profilace, které byly přiděleny v tomto řádku.|  
|**% Výhradních bajtů**|Procento všech počet bajtů paměti, které byly přiděleny při spuštění profilace, které byly přiděleny v tomto řádku.|  
  
## <a name="see-also"></a>Viz také  
 [Zobrazení řádků](../profiling/lines-view-sampling-data.md)



