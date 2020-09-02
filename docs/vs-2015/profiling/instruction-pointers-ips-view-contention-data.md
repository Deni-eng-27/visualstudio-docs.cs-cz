---
title: Zobrazení ukazatelů na instrukce (IP) – data kolizí | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- Instruction Pointers view
ms.assetid: f5e49c24-d4cf-4f87-977d-37e3223d1196
caps.latest.revision: 14
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: b27b185e659fc3a1f0adca4379896543a1eb87ea
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "68187842"
---
# <a name="instruction-pointers-ips-view---contention-data"></a>Zobrazení ukazatelů na instrukce – data kolizí
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Zobrazení IP adres pro data kolizí obsahuje data pro pokyny k sestavení, které se zablokovaly při spuštění profilace.  
  
 V následující tabulce jsou vysvětleny hodnoty sloupců v zobrazení ukazatelů instrukcí.  
  
|Sloupec|Popis|  
|------------|-----------------|  
|**Výhradní čas zablokování**|Čas zablokování této funkce.|  
|**% Výhradního času zablokování**|Procento času zablokování při spuštění instrukce.|  
|**Exkluzivní spory**|Počet sporů, ke kterým došlo během provádění instrukce.|  
|**% Výhradních sporů**|Procento všech sporů v průběhu profilace, ke kterým došlo během provádění instrukcí.|  
|**Adresa funkce**|Počáteční adresa paměti funkce v načteném binárním souboru.|  
|**Název funkce**|Název funkce, která obsahuje instrukci.|  
|**Adresa instrukce**|Adresa paměti instrukce v načteném binárním souboru.|  
|**Číslo řádku funkce**|Číslo řádku začátku této funkce ve zdrojovém souboru.|  
|**Název modulu**|Název modulu, který obsahuje instrukci.|  
|**Cesta k modulu**|Cesta modulu, který obsahuje instrukci.|  
|**ID procesu**|ID procesu (PID) profilované procesu.|  
|**Název procesu**|Název procesu|  
|**Začátek zdrojového znaku**|Posun znaku v řádku zdrojového souboru, na kterém začíná tato instrukce.|  
|**Konec zdrojového znaku**|Posun znaku v řádku zdrojového souboru, na kterém končí tato instrukce|  
|**Zdrojový soubor**|Zdrojový soubor, který obsahuje instrukci.|  
|**Začátek řádku zdroje**|Číslo řádku ve zdrojovém souboru, na kterém začíná tato instrukce.|  
|**Konec řádku zdroje**|Číslo řádku ve zdrojovém souboru, na kterém končí tato instrukce.|  
  
## <a name="see-also"></a>Viz také  
 [Postupy: přizpůsobení sloupců zobrazení sestavy](../profiling/how-to-customize-report-view-columns.md)   
 [Zobrazení ukazatelů na instrukce (IP)](../profiling/instruction-pointers-ips-view.md)   
 [Zobrazení ukazatelů na instrukce (IP) – vzorkování](../profiling/instruction-pointers-ips-view-dotnet-memory-sampling-data.md)   
 [Zobrazení Ukazatele na instrukce (IP)](../profiling/instruction-pointers-ips-view-sampling-data.md)
