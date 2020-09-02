---
title: Zobrazení doby života objektu | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.view.objectlifetime
helpviewer_keywords:
- lifetime, objects
- Objects Lifetime view
- profiling tools reports, Lifetime view
- performance reports, objects lifetime view
- profiling tools, Lifetime view
ms.assetid: d0501fdd-4b3a-4e74-b6ac-51d950a2e15b
caps.latest.revision: 29
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: ef216c1220cbfda37da579d3ea2dfdd32837ab75
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/02/2020
ms.locfileid: "68195558"
---
# <a name="object-lifetime-view"></a>Zobrazení doby života objektu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Zobrazení životnosti objektů je k dispozici, když je také zaškrtnuto políčko **shromažďovat data o životnosti objektů .NET** na stránkách vlastností výkonnostní relace.  
  
 Systém uvolňování paměti [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] spravuje přidělování a uvolňování paměti pro vaši aplikaci. Pro optimalizaci výkonu uvolňování paměti je spravovaná halda rozdělená na tři generace: 0, 1 a 2. Uvolňování paměti modulu runtime ukládá nové objekty v generaci 0. Objekty, které zůstávají kolekce, jsou povýšeny a uloženy v generacích 1 a 2.  
  
 Uvolňování paměti uvolňuje paměť uvolněním celé generace objektů. Pro objekty, které byly vytvořeny profilované aplikace, zobrazuje zobrazení životnost objektů počet a velikost objektů a generování, ve kterém jsou uvolněny.  
  
## <a name="general"></a>Obecné  
  
|Sloupec|Popis|  
|------------|-----------------|  
|**Název třídy**|Název třídy přiděleného typu.|  
|**ID procesu**|ID procesu běhu profilace.|  
|**Název procesu**|Název procesu|  
|**Název modulu**|Název modulu, který obsahuje funkci.|  
|**Cesta k modulu**|Cesta modulu, který obsahuje funkci.|  
  
## <a name="instance-data"></a>Data instance  
 Data instance označují počet objektů typu, které byly vytvořeny v procesu profilace, a generaci, ve kterém byly objekty uvolněny systémem uvolňování paměti.  
  
|Sloupec|Popis|  
|------------|-----------------|  
|**Instance**|Počet přidělení objektů tohoto typu.|  
|**Celkem instancí%**|Procentuální podíl celkového počtu přidělení provedených při spuštění profilace.|  
|**Shromážděné instance gen 0**|Počet instancí typu, které byly navráceny v generaci 0 algoritmu uvolňování paměti.|  
|**Shromážděné instance Gen 1**|Počet instancí typu, které byly navráceny v generaci 1 algoritmu uvolňování paměti.|  
|**Shromážděné instance Gen 2**|Počet instancí typu, které byly navráceny v generaci 2 algoritmu uvolňování paměti.|  
|**Instance aktivní na konci**|Počet instancí typu, které nebyly uvolněny až do konce profilace.|  
  
## <a name="size-byte-data"></a>Velikost (Byte) dat  
 Velikost (Byte) data označuje velikost objektů typu, které byly vytvořeny při spuštění profilování, a množství paměti, které bylo v každé generaci, ve kterém byly objekty uvolněny, uvolněno.  
  
|Sloupec|Popis|  
|------------|-----------------|  
|**Celkový počet přidělených bajtů**|Celkový počet bajtů pro všechny instance daného typu.|  
|**Celkem bajtů v%**|Procentuální podíl celkového počtu přidělených bajtů v běhu profilace, které byly přiděleny pro instance tohoto typu.|  
|**Shromážděné bajty gen 0**|Velikost instancí typu, které byly navráceny v generaci 0 algoritmu uvolňování paměti.|  
|**Shromážděné bajty Gen 1**|Velikost instancí typu, které byly navráceny v generaci 1 algoritmu uvolňování paměti.|  
|**Shromážděné bajty Gen 2**|Velikost instancí typu, které byly navráceny v generaci 2 algoritmu uvolňování paměti.|  
  
## <a name="large-object-heap-data"></a>Large Object dat haldy  
 Alokátor paměti .NET spravuje velmi velké objekty v umístění, které je oddělené od standardní spravované haldy. Data haldy velkých objektů označují počet a velikost objektů typu, které byly spravovány v tomto umístění.  
  
|Sloupec|Popis|  
|------------|-----------------|  
|**Shromážděné instance haldy Large Object**|Počet instancí tohoto typu, které byly umístěny v haldě velkých objektů a které byly shromážděny při spuštění profilace.|  
|**Shromážděné bajty haldy Large Object**|Velikost instancí tohoto typu (v bajtech), které byly umístěny v haldě velkých objektů a které byly shromážděny při spuštění profilace.|  
  
## <a name="see-also"></a>Viz také  
 [Zobrazení dat paměti .NET](../profiling/dotnet-memory-data-views.md)
