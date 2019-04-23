---
title: Trasování událostí pro Windows (ETW) sestavu | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- Event tracing for Windows profiling report
- ETW profiling report
ms.assetid: 81e88162-b88a-40b6-8b85-a232c8096a47
caps.latest.revision: 17
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 5bfcb10bdbbfcb8e4b98f8d90d6652832059107d
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60108214"
---
# <a name="event-tracing-for-windows-etw-report"></a>Trasování událostí pro Windows – sestava
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Sestava trasování událostí pro Windows (ETW) obsahuje události trasování událostí pro Windows, které byly zaznamenány během relace výkonu z [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] nástroje pro profilaci. Data trasování událostí pro Windows se shromažďují v souboru binárního souboru (.etl).  
  
> [!NOTE]
>  Nelze zobrazit sestavy trasování událostí pro Windows v [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] rozhraní.  
  
- Informace o tom, jak shromažďování trasování událostí pro Windows pomocí nástrojů pro profilaci z [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] rozhraní najdete v tématu [jak: Shromažďování trasování událostí pro Windows (ETW) Data](../profiling/how-to-collect-event-tracing-for-windows-etw-data.md).  
  
- Informace o tom, jak shromažďovat data trasování událostí pro Windows s použitím [VSPerfCmd](../profiling/vsperfcmd.md) nástroje příkazového řádku, naleznete v tématu [události](../profiling/events-vsperfcmd.md).  
  
- Generování sestavy trasování událostí pro Windows pomocí **VSReport / Summary: ETW** příkazu. Další informace najdete v tématu [VSPerfReport](../profiling/vsperfreport.md).  
  
|Sloupec|Popis|  
|------------|-----------------|  
|**Časové razítko**|Určuje, kdy došlo k události.|  
|**ID procesu**|Identifikuje proces, který událost vyvolal.|  
|**ID vlákna**|Identifikuje vlákno, které vygenerovalo událost.|  
|**Popis**|Identifikuje zprostředkovatel událostí.|  
|**Typ**|Určuje typ události.|  
|**Vlastnosti**|Vlastnosti události. Každá událost představuje oddělených čárkou, název hodnota pár, který je uzavřen do závorek.|
