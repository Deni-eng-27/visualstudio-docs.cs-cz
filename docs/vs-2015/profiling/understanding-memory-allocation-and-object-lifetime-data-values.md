---
title: Princip přidělování paměti a životnosti objektů hodnot | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- .NET memory profiling method
- Profiling Tools, .NET memory method
ms.assetid: a22445b3-39a6-4919-8506-2b5b0ceaf77e
caps.latest.revision: 16
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 816f750148cc30de86fc116f80f64b218b4699d0
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60069742"
---
# <a name="understanding-memory-allocation-and-object-lifetime-data-values"></a>Princip přidělování paměti a hodnot životnosti objektů
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

*Alokaci paměti .NET* metodu profilace [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] nástrojů pro profilaci sady shromažďuje informace o velikost a počet objektů, které byly vytvořeny během přidělování nebo zničeny v procesu uvolnění paměti a další informace o funkci *zásobníku volání* kdy došlo k události. A *zásobníku volání* je dynamické strukturu, která uchovává informace o funkcích, které jsou spuštěny na procesor.  
  
 **Požadavky**  
  
- [!INCLUDE[vsUltLong](../includes/vsultlong-md.md)], [!INCLUDE[vsPreLong](../includes/vsprelong-md.md)], [!INCLUDE[vsPro](../includes/vspro-md.md)]  
  
  Profilování paměti přerušuje procesor počítače při každém přidělení objektu rozhraní .NET Framework v profilované aplikaci. Při shromažďování dat o době životnosti objektu přerušuje profiler procesor po každém uvolnění paměti rozhraní .NET Framework. Pro každou funkci PROFILOVANÉHO a pro každý typ objektu se data agregují.  
  
## <a name="allocation-data"></a>Data o přidělování  
 Při výskytu události .memory celkové počty a velikosti paměti přidělené nebo zničení objektů jsou zvětšeny.  
  
 Při výskytu události přidělení .memory profiler zvýší čítače vzorků pro každou funkci v zásobníku volání. Když se data shromažďují, pouze jedna funkce v zásobníku volání je aktuálně spouští kód v těle jeho funkce. Další funkce v zásobníku jsou nadřazené položky v hierarchii volání funkce, která čekají na funkce, které jsou volána k vrácení.  
  
- Pro události přidělení, profiler přírůstky *exkluzivní* počet funkce, která se právě probíhá jeho pokynů vzorků. Protože exkluzivní ukázky je také součástí celkové (*včetně*) ukázky funkce, včetně ukázkové počet aktuálně aktivních funkce se také zvýší.  
  
- Profiler zvýší počet vzorků včetně všech funkcí v zásobníku volání.  
  
## <a name="lifetime-data"></a>Data o životním cyklu  
 Uvolňování paměti rozhraní .NET Framework spravuje přidělování a uvolňování paměti pro vaši aplikaci. Za účelem optimalizace výkonu systému uvolňování paměti spravované haldy rozdělen na tři generace: 0, 1 a 2. Doba běhu v systému uvolňování paměti uloží nové objekty 0. generace. Objekty, které byly zachovány při kolekce jsou povýšeny a uloženy v generace 1 a 2.  
  
 Získá systém uvolňování paměti podle rušení přidělení celé generace objektů. Pro objekty, které profilovaná aplikace vytvořena zobrazení doba života objektu zobrazí počet a velikost objektů a jeho generaci při jejich převzetí.
