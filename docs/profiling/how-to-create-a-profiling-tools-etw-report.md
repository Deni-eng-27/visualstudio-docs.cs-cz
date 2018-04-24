---
title: 'Postupy: vytvoření sestavy trasování událostí pro Windows nástrojů pro profilaci | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: bf5547b3-f6c7-4989-9d47-2fe4f1261444
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a49ab3f00eb74edb3be3f733b3c0d70f8613d862
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-create-a-profiling-tools-etw-report"></a>Postupy: Vytvoření sestavy Trasování událostí pro Windows nástrojů pro profilaci
Tato sestava trasování událostí pro Windows (ETW) uvádí události trasování událostí pro Windows, které se zaznamenávají v relaci výkonu z [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] nástrojích pro profilaci. Trasování událostí pro Windows data jsou shromažďována v souboru binárního souboru (ETL). Další informace o této sestavě najdete v tématu [sestavy trasování událostí pro Windows (ETW)](../profiling/event-tracing-for-windows-etw-report.md).  
  
> [!NOTE]
>  Nelze zobrazit sestavy trasování událostí pro Windows v rozhraní pro [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
-   Informace o tom, jak shromažďování dat trasování událostí pro Windows pomocí rozhraní pro [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], najdete v části [postup: Data shromažďovat trasování událostí pro Windows (ETW)](../profiling/how-to-collect-event-tracing-for-windows-etw-data.md).  
  
-   Informace o tom, jak shromažďování dat trasování událostí pro Windows z příkazového řádku najdete v tématu [VSPerfCmd](../profiling/vsperfcmd.md) a [události](../profiling/events-vsperfcmd.md).  
  
 Vygenerování sestavy trasování událostí pro Windows pomocí **VSReport / souhrn: etw** příkaz. ETL, který obsahuje data trasování událostí pro Windows musí být ve stejném adresáři jako profilování datový soubor (.vsp nebo .vsps). Ve výchozím nastavení je sestava generována jako soubor hodnot oddělených čárkami (.csv). Další informace najdete v tématu [vsperfreport –](../profiling/vsperfreport.md).  
  
### <a name="to-generate-an-etw-report"></a>Při generování sestav trasování událostí pro Windows  
  
-   V **příkazového řádku** okno, zadejte následující příkaz:  
  
     *ToolsPath* **vsperfreport –** *VSPFile***/Summary:ETW [XML]**   
  
    |||  
    |-|-|  
    |*ToolsPath*|Cesta nástroj nástrojích pro profilaci. Další informace najdete v tématu [určení cesty k nástrojům příkazového řádku](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md).|  
    |*VSPFile*|Profilování dat (.vsp nebo .vsps) souboru. Úplné a částečné cesty, jsou přijaty.|  
    |XML|V kódu XML generuje sestavy, který je naformátovaný.|