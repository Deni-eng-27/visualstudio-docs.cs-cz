---
title: "Karta Obecné, dialogové okno vlastností vláken | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- threading [Visual Studio], thread properties
- thread properties
ms.assetid: 46b6c668-6786-456e-97dc-337bcac0d812
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: d8d53c373c58e31f2a2719df8afa6dd0da9cd3c6
ms.sourcegitcommit: 9e6ff74da1afd8bd2f0e69387ce81f2a74619182
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/04/2018
---
# <a name="general-tab-thread-properties-dialog-box"></a>Karta Obecné, dialogové okno vlastností vlákna
Další informace o konkrétní vlákno pomocí tohoto dialogového okna. K zobrazení tohoto dialogového okna, přesunout fokus [zobrazení vláken](../debugger/threads-view.md) okno nebo otevřete [zobrazení zpráv](../debugger/messages-view.md) a rozbalte zprávu. Vyberte libovolný uzel přístup z více vláken ve stromové struktuře, a potom vyberte **vlastnosti** z **zobrazení** nabídky.  
  
 **Vláken vlastnosti** dialogové okno obsahuje jeden podokně **Obecné** kartě. K dispozici jsou následující nastavení:  
  
|Položka|Popis|  
|-----------|-----------------|  
|**Název modulu**|Název modulu.|  
|**ID podprocesu**|Jedinečné ID podprocesu. Všimněte si, že ID podprocesu jsou opakovaně využívána; pouze po dobu jeho existence daném vláknu identifikují vlákna.|  
|**ID procesu**|Jedinečný Identifikátor tohoto procesu. Čísla ID procesu jsou opakovaně využívána, takže identifikují proces pouze po dobu jeho existence tohoto procesu. Typ objektu procesu se vytvoří při spuštění programu. Všechny vláken v procesu sdílet stejnou adresní prostor a mít přístup ke stejným datům. Vyberte tuto hodnotu zobrazíte vlastnosti ID procesu.|  
|**Stav vlákna**|Aktuální stav vlákno. Spuštěných vláken používá procesor; Pohotovostní vlákno je použití jedné. Vlákna připravena čeká na použít procesor, protože není volné. Vlákna v přechodném stavu čeká na prostředek provést, jako je například čekání na jeho spuštění zásobník k stránkování v z disku. Čekání na vlákno nemusí procesoru, protože se čeká na dokončení periferní operace nebo prostředek uvolnění.|  
|**Počkejte důvod**|Tuto možnost lze použít pouze v případě, že vlákno je ve stavu čekání. Dvojice hodnot události se používají ke komunikaci s chráněné subsystémy.|  
|**Čas procesoru**|Celkový čas procesoru strávené o tomto procesu a jeho vláken. Rovno uživatelského času + privilegovaného času.|  
|**Uživatelský čas**|Celkem uběhlý čas, který má tohoto podprocesu stráví provádění kódu v uživatelském režimu. Aplikace spouští v uživatelském režimu, stejně jako subsystémy jako správce oken a modulu grafiky.|  
|**Privilegovaného času**|Celkem uběhlý čas, který má tohoto podprocesu stráví provádění kódu v privilegovaném režimu. Když je volána služba systému Windows, služba bude spuštěna často v privilegovaném režimu k získání přístupu k datům vyhrazeným systému. Tato data jsou chráněna před přístupem vlákna spuštěný v uživatelském režimu. Volání do systému může být explicitní nebo mohou být implicitní, například při výskytu chyby stránky nebo přerušení.|  
|**Uplynulý čas**|Celkem uběhlý čas (v sekundách) tohoto podprocesu byla spuštěna.|  
|**Aktuální priorita**|Aktuální dynamické priorita podprocesu. Vlákna v rámci procesu můžete vyvolat a snížit vlastní základní prioritu relativně k základní prioritu procesu.|  
|**Základní prioritu**|Aktuální základní priorita podprocesu.|  
|**Počáteční adresa**|Výchozí virtuální adresu pro tento přístup z více vláken.|  
|**Uživatel počítače**|Čítač uživatele programu pro vlákno.|  
|**Přepnutí kontextu**|Počet přepínače z jedno vlákno na jiný. Vlákno přepínače může dojít v jednom procesu nebo napříč procesy. Vlákno přepínač může být způsobeno jedním vláknem požadující jiné informace, nebo vlákno se zrušené, když se stane vyšší priorita vlákna připravena ke spuštění.|